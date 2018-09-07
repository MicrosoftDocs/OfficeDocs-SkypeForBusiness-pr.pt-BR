---
title: Consultar, alterar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir um ID de conferência a um usuário no Skype for Business Online e quais devem ser os parâmetros de IDs da conferência. '
ms.openlocfilehash: d47e188220f66e320289384c4fbe421328d8eca3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850181"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="3a656-103">Visualizar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a656-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="3a656-104">Para obter informações sobre IDs de conferência de usuários no Microsoft Teams, consulte [Exibir e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="3a656-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="3a656-105">Um ID de conferência é atribuído automaticamente a um usuário do Skype for Business quando está configurado para Audioconferência no Office 365 e usa a Microsoft como o provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="3a656-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="3a656-106">A ID de conferência atribuída é enviada no convite da reunião quando a reunião é agendada.</span><span class="sxs-lookup"><span data-stu-id="3a656-106">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="3a656-107">Cada reunião programada por um usuário receberá um ID de conferência único.</span><span class="sxs-lookup"><span data-stu-id="3a656-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="3a656-108">Embora um ID de conferência seja criado e atribuído a um usuário automaticamente, podem existir ocasiões em que um usuário não deseje usá-lo e você precise configurá-lo para um determinado número, ou seus usuários não lembrem ou tenham perdido o ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="3a656-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="3a656-109">Você pode usar o **centro de administração do Skype for Business** e o Windows PowerShell para exibir, alterar e redefinir o ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="3a656-109">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="3a656-110">Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="3a656-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="3a656-111">Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="3a656-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="3a656-112">Visualizar e redefinir as IDs de conferências</span><span class="sxs-lookup"><span data-stu-id="3a656-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="3a656-113">Para exibir a ID da conferência</span><span class="sxs-lookup"><span data-stu-id="3a656-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="3a656-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="3a656-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="3a656-115">Você pode exibir sua ID de conferência e enviá-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="3a656-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="3a656-116">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="3a656-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3a656-117">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="3a656-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="3a656-118">Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, selecione o usuário que necessita da ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="3a656-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="3a656-119">Na página Ação, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="3a656-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="3a656-120">Você pode enviar todas as informações da conferência para o usuário em um email que inclua a ID da conferência e os números de telefone de áudio clicando no link **Enviar informações da conferência via email** depois de selecionar o usuário na página **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3a656-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="3a656-121">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3a656-121">\*\*\*\* Using Windows PowerShell</span></span>

<span data-ttu-id="3a656-122">Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="3a656-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="3a656-123">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="3a656-123">To do so:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="3a656-124">Para redefinir a ID de conferência da reunião</span><span class="sxs-lookup"><span data-stu-id="3a656-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="3a656-125">É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.</span><span class="sxs-lookup"><span data-stu-id="3a656-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="3a656-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="3a656-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="3a656-127">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="3a656-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3a656-128">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="3a656-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="3a656-129">Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, no painel Ação em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="3a656-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="3a656-130">Na janela **Redefinir o ID da conferência?** , clique **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3a656-130">In the \*\* Reset conference ID?\*\* window, click **Yes**.</span></span> <span data-ttu-id="3a656-131">Uma ID de conferência será criada automaticamente e um email será enviado ao usuário com a nova ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="3a656-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="3a656-132">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3a656-132">\*\*\*\* Using Windows PowerShell</span></span>

<span data-ttu-id="3a656-133">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a656-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="3a656-134">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="3a656-134">To do this run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="3a656-135">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="3a656-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="3a656-136">Depois que uma nova ID de conferência for criada ou for redefinida, a ID antiga não poderá ser usada pelos autores de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3a656-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="3a656-137">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="3a656-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="3a656-138">Os usuários podem usar a Ferramenta de Migração de Reunião do Skype for Business para atualizar suas reuniões marcadas.</span><span class="sxs-lookup"><span data-stu-id="3a656-138">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="3a656-139">Para ver como baixar, instalar e executar a ferramenta, consulte: [Ferramenta de Atualização de Reunião do Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Ferramenta de Migração de Reunião (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047) e [Skype for Business Online, Ferramenta de Migração de Reunião (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="3a656-139">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

- <span data-ttu-id="3a656-140">Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a656-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="3a656-141">A ID da conferência deve atender ao comprimento em dígitos definido na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="3a656-141">The conference ID must meet the length in digits set on the dial-in conferencing bridge.</span></span> <span data-ttu-id="3a656-142">Não é possível usar letras e caracteres especiais nas IDs de conferência, somente números.</span><span class="sxs-lookup"><span data-stu-id="3a656-142">You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span>

- <span data-ttu-id="3a656-143">Por padrão, a ID de conferência de todos os usuários da audioconferência é de sete dígitos e o número de dígitos não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="3a656-143">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3a656-144">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3a656-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3a656-p109">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3a656-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="3a656-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a656-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="3a656-149">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="3a656-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="3a656-p110">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3a656-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="3a656-152">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a656-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="3a656-153">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a656-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="3a656-154">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3a656-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="3a656-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3a656-155">Related topics</span></span>

[<span data-ttu-id="3a656-156">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="3a656-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

