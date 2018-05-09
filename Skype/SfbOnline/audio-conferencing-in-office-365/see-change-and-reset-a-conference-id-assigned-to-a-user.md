---
title: Consulte, alterar e redefina um ID de conferência atribuído a um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 73c5d3cc95b7967cd9d6eaae83a14e19143e431b
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="f3254-103">Visualizar e redefinir uma ID de conferência atribuída a um usuário</span><span class="sxs-lookup"><span data-stu-id="f3254-103">View and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="f3254-104">Uma ID de conferência é atribuída automaticamente a um Skype para usuário de negócios ou Microsoft Teams quando eles estiverem configurados para conferência de áudio no Office 365 e usarem o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3254-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="f3254-105">A ID de conferência atribuída é enviada no convite da reunião, quando a reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="f3254-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="f3254-106">Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="f3254-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="f3254-107">Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="f3254-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="f3254-108">Você pode usar o **Skype para centro de administração de negócios** e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="f3254-108">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="f3254-109">Um email será enviado ao usuário com a ID de conferência e os números de telefone de conferência de áudio padrão, ou se você redefinir o ID de conferência um email diferente será enviado que incluírem o ID de conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="f3254-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="f3254-110">Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="f3254-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="f3254-111">Visualizar e redefinir as IDs de conferência</span><span class="sxs-lookup"><span data-stu-id="f3254-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="f3254-112">Para exibir a ID de conferência</span><span class="sxs-lookup"><span data-stu-id="f3254-112">To view the conference ID</span></span>

<span data-ttu-id="f3254-113">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="f3254-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="f3254-114">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f3254-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f3254-115">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3254-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f3254-116">Em **Conferência de áudio**, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="f3254-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f3254-117">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **Enviar informações de conferência no email** .</span><span class="sxs-lookup"><span data-stu-id="f3254-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="f3254-118">Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="f3254-118">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="f3254-119">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f3254-119">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


<span data-ttu-id="f3254-120">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="f3254-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="f3254-121">Você pode exibir sua ID de conferência e enviá-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="f3254-121">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="f3254-122">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="f3254-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f3254-123">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="f3254-123">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f3254-124">No **Skype para centro de administração de negócios**> **audioconferências** > **usuários**, selecione o usuário que necessidades ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="f3254-124">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="f3254-125">Na página ação, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="f3254-125">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f3254-126">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **Enviar informações de conferência via email** depois de selecionar o usuário na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="f3254-126">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="f3254-127">Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="f3254-127">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="f3254-128">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f3254-128">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="f3254-129">Para redefinir o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="f3254-129">To reset the conference ID</span></span>

<span data-ttu-id="f3254-130">Você pode redefinir uma ID de conferência para um usuário se, por exemplo, caso eles tenha esquecido.</span><span class="sxs-lookup"><span data-stu-id="f3254-130">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
<span data-ttu-id="f3254-131">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="f3254-131">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="f3254-132">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f3254-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f3254-133">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3254-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f3254-134">Em **Conferência de áudio**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="f3254-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="f3254-135">Na janela **Redefinir ID de conferência** , clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="f3254-135">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="f3254-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="f3254-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="f3254-137">Você pode redefinir a ID de conferência para um usuário usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3254-137">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="f3254-138">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f3254-138">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

<span data-ttu-id="f3254-139">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="f3254-139">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="f3254-140">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="f3254-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f3254-141">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="f3254-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f3254-142">No **Skype para centro de administração de negócios**> **audioconferências** > **usuários**, no painel de ação em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="f3254-142">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="f3254-143">No **Redefinir ID de conferência?** janela, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f3254-143">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="f3254-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="f3254-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="f3254-145">Você pode redefinir a ID de conferência para um usuário usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3254-145">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="f3254-146">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f3254-146">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="f3254-147">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="f3254-147">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="f3254-148">Depois que uma nova ID de conferência é criada ou um é redefinido, o ID de conferência antigos não pode ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="f3254-148">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f3254-149">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="f3254-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="f3254-150">Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="f3254-150">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="f3254-151">Para ver como baixar, instalar e executar a ferramenta, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para negócios Online, a ferramenta de migração de reunião (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="f3254-151">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="f3254-152">Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3254-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="f3254-153">A ID de conferência deve atender a duração em dígitos, defina a ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="f3254-153">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="f3254-154">Você não pode usar caracteres alfabéticos ou especiais de conferência IDs; somente números podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="f3254-154">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="f3254-155">O ID de conferência para todos os usuários de serviços de audioconferência será 7 dígitos por padrão, e o número de dígitos não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f3254-155">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f3254-156">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f3254-156">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f3254-p112">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f3254-p112">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f3254-160">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3254-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f3254-161">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="f3254-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f3254-p113">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f3254-p113">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f3254-164">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3254-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f3254-165">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3254-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f3254-166">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3254-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f3254-167">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f3254-167">Related topics</span></span>

[<span data-ttu-id="f3254-168">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="f3254-168">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

