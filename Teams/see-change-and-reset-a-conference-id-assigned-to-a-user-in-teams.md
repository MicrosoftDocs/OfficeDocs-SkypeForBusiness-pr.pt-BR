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
description: Saiba como atribuir uma ID de conferência a um usuário no Microsoft Teams e quais devem ser os parâmetros de IDs de conferência.
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691147"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="c3333-103">Visualizar e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3333-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="c3333-104">Uma ID de conferência é atribuída automaticamente a um usuário do Microsoft Teams quando está configurada para Audioconferência no Microsoft 365 ou no Office 365 e usa a Microsoft como provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c3333-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c3333-105">O ID de conferência atribuído é enviado no convite da reunião quando ela é agendada.</span><span class="sxs-lookup"><span data-stu-id="c3333-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="c3333-106">Cada reunião agendada por um usuário terá um ID de conferência exclusivo atribuído.</span><span class="sxs-lookup"><span data-stu-id="c3333-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="c3333-107">Ainda que um ID de conferência seja automaticamente criado e atribuído ao usuário, poderá haver momentos em que o usuário não desejará usá-lo ou você desejará defini-lo como um número específico, ou quando os usuários se esquecem ou pedem o ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="c3333-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="c3333-108">É possível usar o centro de administração do Microsoft Teams ou o Windows PowerShell para visualizar, alterar e redefinir o ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="c3333-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="c3333-109">Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="c3333-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="c3333-110">Consulte [Redefinir uma ID de conferência para um usuário](reset-a-conference-id-for-a-user-in-teams.md) no Microsoft Teams para obter mais informações sobre como redefinir o PIN de um organizador de conferência.</span><span class="sxs-lookup"><span data-stu-id="c3333-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="c3333-111">Visualizar e redefinir as IDs de conferências</span><span class="sxs-lookup"><span data-stu-id="c3333-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="c3333-112">Para visualizar o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="c3333-112">To view the conference ID</span></span>

<span data-ttu-id="c3333-113">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="c3333-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c3333-114">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c3333-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c3333-115">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3333-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c3333-116">Em **Audioconferência**, veja **ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="c3333-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c3333-117">É possível enviar todas as informações da conferência para o usuário em um e-mail que contém o ID de conferência e os números de telefone de áudio, clicando em **Enviar informações da conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="c3333-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="c3333-118">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c3333-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="c3333-119">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c3333-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="c3333-120">Para redefinir o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="c3333-120">To reset the conference ID</span></span>

<span data-ttu-id="c3333-121">É possível redefinir o ID de conferência para um usuário se ele esquecer o ID, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="c3333-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="c3333-122">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="c3333-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c3333-123">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c3333-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c3333-124">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3333-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c3333-125">Em **Audio conferência**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="c3333-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="c3333-126">Na janela **Redefinir ID de conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="c3333-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="c3333-127">Um ID de conferência será criado automaticamente e um e-mail será enviado ao usuário com o novo ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="c3333-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="c3333-128">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c3333-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="c3333-129">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c3333-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="c3333-130">O que mais você precisa saber?</span><span class="sxs-lookup"><span data-stu-id="c3333-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="c3333-131">Depois que o ID de conferência é redefinido ou um novo é criado, o ID antigo não pode ser usado pelos chamadores.</span><span class="sxs-lookup"><span data-stu-id="c3333-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c3333-132">Você deve notificar os usuários para que reagendem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="c3333-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="c3333-133">O ID de conferência deve seguir o comprimento em dígitos definido na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c3333-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="c3333-134">Não é possível usar letras e caracteres especiais nos IDs de conferência, somente números.</span><span class="sxs-lookup"><span data-stu-id="c3333-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c3333-135">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c3333-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c3333-136">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="c3333-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c3333-137">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="c3333-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c3333-138">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c3333-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c3333-139">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="c3333-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c3333-140">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3333-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="c3333-141">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c3333-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c3333-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c3333-142">Related topics</span></span>

[<span data-ttu-id="c3333-143">Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365</span><span class="sxs-lookup"><span data-stu-id="c3333-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
