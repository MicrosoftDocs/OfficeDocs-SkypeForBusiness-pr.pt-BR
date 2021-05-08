---
title: Consulte, altere e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online
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
description: 'Saiba como atribuir uma ID de conferência a um usuário no Skype for Business Online e quais os parâmetros de IDs de conferência devem ser. '
ms.openlocfilehash: f12982298903485d93582fae3a4f39aaed49170c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237047"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="f3824-103">Visualizar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3824-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="f3824-104">Para obter informações sobre IDs de conferência do usuário no Microsoft Teams, consulte Exibir e redefinir uma [ID](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)de conferência atribuída a um usuário em Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="f3824-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="f3824-105">Uma ID de conferência é atribuída automaticamente a um usuário Skype for Business quando está configurada para Audioconferência no Microsoft 365 ou Office 365 e usa a Microsoft como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3824-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="f3824-106">A ID da conferência atribuída é enviada no convite da reunião quando a reunião é agendada.</span><span class="sxs-lookup"><span data-stu-id="f3824-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="f3824-107">Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.</span><span class="sxs-lookup"><span data-stu-id="f3824-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="f3824-108">Embora uma ID de conferência seja criada e atribuída automaticamente a um usuário, pode haver momentos em que um usuário não deseja usá-la e você deseja defini-la como um determinado número, ou quando seus usuários não puderem se lembrar ou perderem a ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="f3824-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="f3824-109">Você pode usar o Skype for Business **de** administração e Windows PowerShell para exibir, alterar e redefinir a ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="f3824-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="f3824-110">Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="f3824-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="f3824-111">Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="f3824-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="f3824-112">Visualizar e redefinir as IDs de conferências</span><span class="sxs-lookup"><span data-stu-id="f3824-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="f3824-113">Para exibir a ID da conferência</span><span class="sxs-lookup"><span data-stu-id="f3824-113">To view the conference ID</span></span>

<span data-ttu-id="f3824-114">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="f3824-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="f3824-115">Você pode exibir sua ID de conferência e enviá-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="f3824-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="f3824-116">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="f3824-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="f3824-117">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="f3824-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="f3824-118">Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, selecione o usuário que necessita da ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="f3824-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="f3824-119">Na página Ação, procure em **ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="f3824-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f3824-120">Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID da conferência e  números de telefone de áudio clicando no link Enviar informações de conferência por **email** depois de selecionar o usuário na página Usuários.</span><span class="sxs-lookup"><span data-stu-id="f3824-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="f3824-121">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3824-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="f3824-122">Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="f3824-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="f3824-123">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f3824-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="f3824-124">Consulte [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3824-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="f3824-125">Para redefinir a ID da conferência</span><span class="sxs-lookup"><span data-stu-id="f3824-125">To reset the conference ID</span></span>

<span data-ttu-id="f3824-126">É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.</span><span class="sxs-lookup"><span data-stu-id="f3824-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="f3824-127">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="f3824-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="f3824-128">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="f3824-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="f3824-129">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="f3824-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="f3824-130">No centro **de Skype for Business de** administração Usuários de Audioconferência , no painel Ação em ID da >    >  Conferência, clique em **Redefinir**. </span><span class="sxs-lookup"><span data-stu-id="f3824-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="f3824-131">Na janela **Redefinir iD** da conferência? clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f3824-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="f3824-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="f3824-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="f3824-133">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f3824-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="f3824-134">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3824-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="f3824-135">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f3824-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="f3824-136">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="f3824-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="f3824-137">Depois que uma nova ID de conferência é criada ou uma é redefinida, a ID de conferência antiga não pode ser usada pelos chamadores.</span><span class="sxs-lookup"><span data-stu-id="f3824-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f3824-138">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="f3824-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="f3824-139">Os usuários podem usar o Skype for Business de Migração de Reunião para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="f3824-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="f3824-140">Para ver como baixar, instalar e executar a ferramenta, consulte: Meeting [Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype for Business [Online, Meeting Migration Tool (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business Online, Meeting Migration Tool (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="f3824-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="f3824-141">Consulte [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3824-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="f3824-142">A ID da conferência deve atender ao comprimento em dígitos definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f3824-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="f3824-143">Não é possível usar caracteres alfabéticos ou especiais em IDs de conferência; somente números podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="f3824-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="f3824-144">A ID da conferência para todos os usuários de audioconferência será de 9 dígitos por padrão, e o número de dígitos não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f3824-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f3824-145">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f3824-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f3824-146">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer.</span><span class="sxs-lookup"><span data-stu-id="f3824-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f3824-147">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="f3824-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f3824-148">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f3824-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="f3824-149">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3824-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="f3824-150">Por que você precisa usar Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3824-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="f3824-151">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f3824-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f3824-152">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f3824-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="f3824-153">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f3824-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="f3824-154">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3824-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="f3824-155">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3824-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="f3824-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f3824-156">Related topics</span></span>

[<span data-ttu-id="f3824-157">Experimente ou compre Audioconferência em Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="f3824-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
