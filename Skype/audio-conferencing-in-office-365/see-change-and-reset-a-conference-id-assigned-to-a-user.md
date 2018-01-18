---
title: "Consulte, alterar e redefina um ID de conferência atribuído a um usuário"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to assign a conference ID to a user in Skype for Business and what the conference ID''s parameters should be. '
ms.openlocfilehash: 46edf684a835984524ce988da532b6b9a14931da
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="5cfc4-103">Consulte, alterar e redefina um ID de conferência atribuído a um usuário</span><span class="sxs-lookup"><span data-stu-id="5cfc4-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="5cfc4-104">Uma ID de conferência é atribuída automaticamente a um Skype para usuário de negócios ou Microsoft Teams quando eles estiverem configurados para conferência de áudio no Office 365 e usarem o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="5cfc4-105">A ID de conferência atribuída pode ser estáticos ou dinâmicos e é enviada no convite da reunião, quando a reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="5cfc4-106">IDs estáticas são usadas quando as pessoas na sua organização não desejam Lembre-se de um número aleatório; eles podem selecionar um certo número ou use um que seja fácil de lembrar.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="5cfc4-107">Quando IDs de conferência dinâmicos são usados, cada reunião agendas de um usuário serão obtido atribuída uma ID de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="5cfc4-108">Se você deseja atribuir dinâmico em vez de conferência estática IDs, [acesse aqui](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="5cfc4-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="5cfc4-109">Embora uma ID de conferência estática será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="5cfc4-110">Você pode usar o **Skype para centro de administração de negócios** e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="5cfc4-111">Um email será enviado ao usuário com a ID de conferência e os números de telefone de conferência de áudio padrão, ou se você redefinir o ID de conferência um email diferente será enviado que incluírem o ID de conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="5cfc4-112">Exibir e alterar as IDs de conferência</span><span class="sxs-lookup"><span data-stu-id="5cfc4-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="5cfc4-113">Para exibir a ID de conferência</span><span class="sxs-lookup"><span data-stu-id="5cfc4-113">To view the conference ID</span></span>

<span data-ttu-id="5cfc4-114">Você pode exibir sua ID de conferência e enviá-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="5cfc4-115">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5cfc4-116">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5cfc4-117">No **Skype para centro de administração de negócios**> **audioconferências** > **usuários**, selecione o usuário que necessidades ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="5cfc4-118">Na página ação, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5cfc4-119">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **Enviar informações de conferência via email** depois de selecionar o usuário na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="5cfc4-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="5cfc4-120">Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="5cfc4-121">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="5cfc4-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="5cfc4-122">Consulte [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="5cfc4-123">Para atribuir ou alterar a ID de conferência</span><span class="sxs-lookup"><span data-stu-id="5cfc4-123">To assign or change the conference ID</span></span>

<span data-ttu-id="5cfc4-124">Você pode atribuir ou alterar um ID de conferência para um usuário se, por exemplo, alguém uma ID de conferência que é fácil de lembrar.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5cfc4-125">O Skype para centro de administração de negócios não pode ser usado para editar uma ID de conferência que foi criada automaticamente, mas você pode usar o Windows PowerShell para editar ou alterar uma ID de conferência que você definiu.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="5cfc4-126">Para editar ou alterar a ID de conferência para um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="5cfc4-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="5cfc4-127">Uma ID de conferência deve conter 7 dígitos, e você não pode alterá-lo no Skype para centro de administração de negócios ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="5cfc4-128">Para redefinir o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="5cfc4-128">To reset the conference ID</span></span>

<span data-ttu-id="5cfc4-129">Você pode redefinir uma ID de conferência para um usuário se, por exemplo, caso eles tenha esquecido.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="5cfc4-130">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5cfc4-131">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5cfc4-132">No **Skype para centro de administração de negócios**> **audioconferências** > **usuários**, no painel de ação em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="5cfc4-133">No **Redefinir ID de conferência?** janela, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="5cfc4-134">Uma conferência que ID será criado automaticamente e um email enviado ao usuário com a nova ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="5cfc4-135">Você pode redefinir a ID de conferência para um usuário usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="5cfc4-136">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="5cfc4-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="5cfc4-137">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="5cfc4-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="5cfc4-138">Depois que uma nova ID de conferência é criada ou um é redefinido, o ID de conferência antigos não pode ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5cfc4-139">Você deverá notificar os usuários a reprogramar seus convites para se certificar de que a nova conferência que ID é adicionada para os convites de reunião existente.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="5cfc4-140">Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="5cfc4-141">Para ver como baixar, instalar e executar a ferramenta, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para negócios Online, a ferramenta de migração de reunião (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="5cfc4-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="5cfc4-142">Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="5cfc4-143">A ID de conferência deve atender a duração em dígitos, defina a ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="5cfc4-144">Você não pode usar caracteres alfabéticos ou especiais de conferência IDs; somente números podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="5cfc4-145">O ID de conferência para todos os usuários de serviços de audioconferência será 7 dígitos por padrão, e o número de dígitos não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
- <span data-ttu-id="5cfc4-146">Se o usuário é movido do Microsoft como um provedor de serviços de audioconferência para um provedor de serviços de audioconferência de terceiros ou o provedor de serviços de audioconferência estiver definido como **Nenhuma**, o ID de conferência não funcionará mais.</span><span class="sxs-lookup"><span data-stu-id="5cfc4-146">If the user is moved from Microsoft as the audio conferencing provider to a third-party audio conferencing provider or the audio conferencing provider is set to **None**, the conference ID will no longer work.</span></span> <span data-ttu-id="5cfc4-147">Consulte [atribuir um terceiro como um provedor de serviços de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md) ou [movimentação de provedor de serviços de audioconferência do usuário à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5cfc4-147">See [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) or [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5cfc4-148">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5cfc4-148">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5cfc4-p110">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5cfc4-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5cfc4-152">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5cfc4-152">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5cfc4-153">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="5cfc4-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5cfc4-p111">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5cfc4-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5cfc4-156">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cfc4-156">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5cfc4-157">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5cfc4-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5cfc4-158">Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5cfc4-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="5cfc4-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5cfc4-159">Related topics</span></span>

[<span data-ttu-id="5cfc4-160">Configurar a Audioconferência para o Skype for Business e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5cfc4-160">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

