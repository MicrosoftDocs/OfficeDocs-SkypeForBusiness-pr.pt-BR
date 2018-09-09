---
title: Consulte, alterar e redefinir uma ID de conferência atribuída a um usuário no Skype para Business Online
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir uma ID de conferência para um usuário no Skype para Business Online e quais devem ser os parâmetros de IDs de conferência. '
ms.openlocfilehash: 7996cc91bd9461f733f82da3eb01eeac7109604a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883411"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="54087-103">Visualizar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="54087-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="54087-104">Para obter informações sobre IDs de conferência de usuários no Microsoft Teams, consulte [Exibir e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="54087-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="54087-105">Um ID de conferência é atribuído automaticamente a um usuário do Skype for Business quando está configurado para Audioconferência no Office 365 e usa a Microsoft como o provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="54087-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="54087-106">A ID de conferência atribuída é enviada no convite da reunião, quando a reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="54087-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="54087-107">Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="54087-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="54087-108">Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="54087-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="54087-109">Você pode usar o **Skype para centro de administração de negócios** e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="54087-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="54087-110">Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="54087-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="54087-111">Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="54087-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="54087-112">Visualizar e redefinir as IDs de conferências</span><span class="sxs-lookup"><span data-stu-id="54087-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="54087-113">Para exibir a ID de conferência</span><span class="sxs-lookup"><span data-stu-id="54087-113">To view the conference ID</span></span>

<span data-ttu-id="54087-114">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="54087-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="54087-115">Você pode exibir sua ID de conferência e enviá-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="54087-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="54087-116">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="54087-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="54087-117">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="54087-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="54087-118">Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, selecione o usuário que necessita da ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="54087-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="54087-119">Na página Ação, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="54087-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="54087-120">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **Enviar informações de conferência via email** depois de selecionar o usuário na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="54087-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="54087-121">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="54087-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="54087-122">Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="54087-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="54087-123">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="54087-123">To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="54087-124">Para redefinir o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="54087-124">To reset the conference ID</span></span>

<span data-ttu-id="54087-125">É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.</span><span class="sxs-lookup"><span data-stu-id="54087-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="54087-126">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="54087-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="54087-127">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="54087-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="54087-128">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="54087-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="54087-129">No **Skype para centro de administração de negócios**> **audioconferências** > **usuários**, no painel de ação em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="54087-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="54087-130">No **Redefinir ID de conferência?** janela, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="54087-130">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="54087-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="54087-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="54087-132">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="54087-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="54087-133">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54087-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="54087-134">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="54087-134">To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="54087-135">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="54087-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="54087-136">Depois que uma nova ID de conferência é criada ou um é redefinido, o ID de conferência antigos não pode ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="54087-136">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="54087-137">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="54087-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="54087-138">Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="54087-138">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="54087-139">Para ver como baixar, instalar e executar a ferramenta, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para negócios Online, a ferramenta de migração de reunião (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="54087-139">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="54087-140">Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="54087-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="54087-141">A ID de conferência deve atender a duração em dígitos, defina a ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="54087-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="54087-142">Você não pode usar caracteres alfabéticos ou especiais de conferência IDs; somente números podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="54087-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="54087-143">O ID de conferência para todos os usuários de serviços de audioconferência será 7 dígitos por padrão, e o número de dígitos não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="54087-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="54087-144">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="54087-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="54087-p109">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="54087-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="54087-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="54087-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="54087-149">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="54087-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="54087-p110">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="54087-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="54087-152">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54087-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="54087-153">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="54087-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="54087-154">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="54087-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="54087-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="54087-155">Related topics</span></span>

[<span data-ttu-id="54087-156">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="54087-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

