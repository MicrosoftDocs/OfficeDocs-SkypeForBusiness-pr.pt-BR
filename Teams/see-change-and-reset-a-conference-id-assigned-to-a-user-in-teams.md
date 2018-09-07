---
title: Consulte, alterar e redefinir uma ID de conferência atribuída a um usuário no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Saiba como atribuir uma ID de conferência para um usuário no Microsoft Teams e que a conferência IDs parâmetros deveria. '
ms.openlocfilehash: aa69788e86689fb393684bfb9367152269cfa457
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850937"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="51c12-103">Visualizar e redefinir uma ID de conferência atribuída a um usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51c12-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="51c12-104">Uma ID de conferência é automaticamente atribuída a um usuário do Microsoft Teams quando eles estiverem configurados para conferência de áudio no Office 365 e usarem o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="51c12-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="51c12-105">A ID de conferência atribuída é enviada no convite da reunião, quando a reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="51c12-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="51c12-106">Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="51c12-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="51c12-107">Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="51c12-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="51c12-108">Você pode usar o Centro de administração do Microsoft Teams ou o Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="51c12-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="51c12-109">Um email será enviado ao usuário com a ID de conferência e os números de telefone de conferência de áudio padrão, ou se você redefinir o ID de conferência um email diferente será enviado que incluírem o ID de conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="51c12-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="51c12-110">Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="51c12-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="51c12-111">Visualizar e redefinir as IDs de conferência</span><span class="sxs-lookup"><span data-stu-id="51c12-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="51c12-112">Para exibir a ID de conferência</span><span class="sxs-lookup"><span data-stu-id="51c12-112">To view the conference ID</span></span>

<span data-ttu-id="51c12-113">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="51c12-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="51c12-114">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="51c12-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="51c12-115">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51c12-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="51c12-116">Em **Conferência de áudio**, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="51c12-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="51c12-117">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **Enviar informações de conferência no email** .</span><span class="sxs-lookup"><span data-stu-id="51c12-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="51c12-118">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="51c12-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="51c12-119">Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="51c12-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="51c12-120">Para redefinir o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="51c12-120">To reset the conference ID</span></span>

<span data-ttu-id="51c12-121">Você pode redefinir uma ID de conferência para um usuário se, por exemplo, esquecer.</span><span class="sxs-lookup"><span data-stu-id="51c12-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="51c12-122">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="51c12-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="51c12-123">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="51c12-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="51c12-124">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51c12-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="51c12-125">Em **Conferência de áudio**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="51c12-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="51c12-126">Na janela **Redefinir ID de conferência** , clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="51c12-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="51c12-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="51c12-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="51c12-128">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="51c12-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="51c12-129">Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="51c12-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="51c12-130">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="51c12-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="51c12-131">Depois que uma nova ID de conferência é criada ou um é redefinido, o ID de conferência antigos não pode ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="51c12-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="51c12-132">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="51c12-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="51c12-133">A ID de conferência deve atender a duração em dígitos, defina a ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="51c12-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="51c12-134">Você não pode usar caracteres alfabéticos ou especiais de conferência IDs; somente números podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="51c12-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="51c12-135">O ID de conferência para todos os usuários de serviços de audioconferência será 7 dígitos por padrão, e o número de dígitos não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="51c12-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="51c12-136">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="51c12-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="51c12-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="51c12-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="51c12-140">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="51c12-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="51c12-141">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51c12-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="51c12-142">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="51c12-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="51c12-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="51c12-143">Related topics</span></span>

[<span data-ttu-id="51c12-144">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="51c12-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

