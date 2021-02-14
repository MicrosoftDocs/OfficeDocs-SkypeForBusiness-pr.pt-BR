---
title: Iniciar uma audioconferência por telefone sem um PIN no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Aprender a habilitar ou desabilitar chamadores anônimos para ingressar em uma reunião a partir do centro de administração Skype for Business ou usando um script do PowerShell. '
ms.openlocfilehash: f02d458450f07b64f3daf4d23b1c56aa2bb846a3
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163870"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="77c1d-103">Iniciar uma audioconferência por telefone sem um PIN no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="77c1d-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="77c1d-104">Para obter informações sobre como iniciar uma audioconferência de áudio sem um PIN no Microsoft Teams, consulte [Iniciar uma audioconferência de áudio por telefone sem um PIN no Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="77c1d-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="77c1d-105">Pode ser frustrante para os usuários que discam para uma reunião serem realizadas no lobby da reunião ouvindo música porque o organizador da reunião do Skype for Business ainda não iniciou a reunião.</span><span class="sxs-lookup"><span data-stu-id="77c1d-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="77c1d-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span><span class="sxs-lookup"><span data-stu-id="77c1d-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="77c1d-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="77c1d-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="77c1d-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span><span class="sxs-lookup"><span data-stu-id="77c1d-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="77c1d-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="77c1d-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="77c1d-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="77c1d-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="77c1d-113">Habilitar ou desabilitar chamadores anônimos para participar de uma reunião</span><span class="sxs-lookup"><span data-stu-id="77c1d-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="77c1d-114">No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para Usuários de **Audioconferência.**  >  </span><span class="sxs-lookup"><span data-stu-id="77c1d-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="77c1d-115">Na lista, selecione o usuário e, no painel Ação, clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="77c1d-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="77c1d-116">Na página de propriedades do usuário, em Opções de **Reunião,** marque ou des clear **Allow unauthenticated callers to be the first people in a meeting. Caso não o seja, eles aguardarão no lobby até que um usuário autenticado in joins.**</span><span class="sxs-lookup"><span data-stu-id="77c1d-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="77c1d-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="77c1d-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="77c1d-118">**Usando o Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="77c1d-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="77c1d-119">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="77c1d-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="77c1d-120">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="77c1d-120">What else should you know?</span></span>

- <span data-ttu-id="77c1d-121">Se você quiser redefinir o PIN, consulte [Redefinir o PIN de Audioconferência.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="77c1d-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="77c1d-122">Se o acesso anônimo, ou não exigir um PIN para iniciar uma reunião, será desabilitado:</span><span class="sxs-lookup"><span data-stu-id="77c1d-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="77c1d-123">Se a reunião ainda não tiver começado (não há ninguém na reunião): um chamador será solicitado se ele for o organizador; se ele disser que sim, ele será solicitado a inserir o PIN e, depois de inserir o PIN, a reunião será iniciar e o usuário ingressará na reunião.</span><span class="sxs-lookup"><span data-stu-id="77c1d-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="77c1d-124">Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.</span><span class="sxs-lookup"><span data-stu-id="77c1d-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="77c1d-125">Se o acesso anônimo, ou não exigir um PIN para iniciar uma reunião, estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="77c1d-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="77c1d-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span><span class="sxs-lookup"><span data-stu-id="77c1d-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="77c1d-128">Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.</span><span class="sxs-lookup"><span data-stu-id="77c1d-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="77c1d-129">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="77c1d-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="77c1d-130">Para economizar tempo e automatizar a tarefa para mais de um usuário, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="77c1d-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="77c1d-p104">No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que os usuários podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="77c1d-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77c1d-134">Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="77c1d-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="77c1d-135">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77c1d-135">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="77c1d-p105">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações nas configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="77c1d-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="77c1d-138">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="77c1d-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="77c1d-139">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="77c1d-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="77c1d-140">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="77c1d-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="77c1d-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="77c1d-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="77c1d-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="77c1d-143">Related topics</span></span>

[<span data-ttu-id="77c1d-144">Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365</span><span class="sxs-lookup"><span data-stu-id="77c1d-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
