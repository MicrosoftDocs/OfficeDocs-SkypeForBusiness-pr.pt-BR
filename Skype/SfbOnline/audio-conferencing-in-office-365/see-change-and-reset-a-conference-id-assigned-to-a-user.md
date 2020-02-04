---
title: Ver, alterar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir uma ID de conferência a um usuário no Skype for Business Online e o que os parâmetros de IDs de conferência devem estar. '
ms.openlocfilehash: 84218fefb831e37255e7049e082f7fe715dc0eb4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680448"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="4d430-103">Visualizar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d430-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="4d430-104">Para obter informações sobre as IDs de conferência do usuário no Microsoft Teams, consulte [Exibir e redefinir uma ID de conferência atribuída a um usuário no Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4d430-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="4d430-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="4d430-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="4d430-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="4d430-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="4d430-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="4d430-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="4d430-112">Visualizar e redefinir as IDs de conferências</span><span class="sxs-lookup"><span data-stu-id="4d430-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="4d430-113">Para exibir a ID de conferência</span><span class="sxs-lookup"><span data-stu-id="4d430-113">To view the conference ID</span></span>

<span data-ttu-id="4d430-114">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="4d430-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="4d430-115">Você pode exibir sua ID de conferência e enviá-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="4d430-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="4d430-116">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="4d430-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4d430-117">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4d430-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4d430-118">Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, selecione o usuário que necessita da ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="4d430-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="4d430-119">Na página Ação, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="4d430-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4d430-120">Você pode enviar todas as informações da conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **enviar informações da conferência por email** depois de selecionar o usuário na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="4d430-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="4d430-121">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4d430-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4d430-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="4d430-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```PowerShell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="4d430-124">Para redefinir a ID de conferência</span><span class="sxs-lookup"><span data-stu-id="4d430-124">To reset the conference ID</span></span>

<span data-ttu-id="4d430-125">É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.</span><span class="sxs-lookup"><span data-stu-id="4d430-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="4d430-126">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="4d430-126">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4d430-127">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="4d430-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4d430-128">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4d430-128">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4d430-129">Nos**usuários**de> **videoconferência** > do **centro de administração do Skype for Business**, no painel ação em **ID de conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="4d430-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="4d430-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4d430-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="4d430-132">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4d430-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4d430-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="4d430-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="4d430-135">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="4d430-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="4d430-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="4d430-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="4d430-140">Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4d430-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="4d430-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span><span class="sxs-lookup"><span data-stu-id="4d430-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="4d430-143">A ID de conferência para todos os seus usuários de audioconferência serão 7 dígitos por padrão e o número de dígitos não poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="4d430-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4d430-144">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4d430-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4d430-p109">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4d430-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="4d430-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d430-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="4d430-149">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="4d430-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="4d430-p110">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="4d430-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="4d430-152">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d430-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="4d430-153">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d430-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="4d430-154">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d430-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="4d430-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4d430-155">Related topics</span></span>

[<span data-ttu-id="4d430-156">Experimentar ou comprar audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="4d430-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

