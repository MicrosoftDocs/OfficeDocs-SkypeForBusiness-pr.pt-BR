---
title: Iniciar uma conferência de áudio por telefone sem um PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 7c6f0e70780b04e75be52ead1eaf08602bcba003
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="947ab-103">Iniciar uma conferência de áudio por telefone sem um PIN</span><span class="sxs-lookup"><span data-stu-id="947ab-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="947ab-104">Talvez seja frustrante para usuários que discam para uma reunião para ser mantidos no lobby da reunião escutando música porque o Skype para negócios ou Microsoft Teams organizador da reunião não tiver iniciado a reunião.</span><span class="sxs-lookup"><span data-stu-id="947ab-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="947ab-105">Se o organizador da reunião chama reunião, por padrão, é necessário um PIN para iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="947ab-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="947ab-106">Você pode montá-lo para que qualquer pessoa pode discar para uma reunião e não ser solicitado a fornecer um PIN para iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="947ab-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="947ab-107">Você pode usar o Centro de administração do Skype for Business para habilitar ou desabilitar essa configuração para um único usuário.</span><span class="sxs-lookup"><span data-stu-id="947ab-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="947ab-108">Um PIN não é necessário para o organizador da reunião, se alguém tiver iniciado a reunião de um Skype para aplicativo de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="947ab-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="947ab-109">É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="947ab-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="947ab-110">O PIN para reuniões é enviado ao usuário áudio quando eles recebem a licença de **Serviços de audioconferência** e estão habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="947ab-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="947ab-111">Consulte [Enviar um email a um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md) e [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="947ab-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="947ab-112">Habilitar ou desabilitar chamadores anônimos para participar de uma reunião</span><span class="sxs-lookup"><span data-stu-id="947ab-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="947ab-113">**Usando equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="947ab-113">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="947ab-114">No painel de navegação esquerdo, clique em **usuários**.</span><span class="sxs-lookup"><span data-stu-id="947ab-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="947ab-115">Selecione um usuário na lista e clique em **Editar** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="947ab-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="947ab-116">Clique no menu ao lado de **Pontes de conferência**e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="947ab-116">Click the menu next to **Conference Bridges**, and then click **Edit**.</span></span>

4. <span data-ttu-id="947ab-117">No painel de tarefas do **provedor de ponte de conferência** , habilite ou desabilite **chamadores de permitir não autenticado para ser as primeira pessoas em uma reunião. Se não, em seguida, eles aguardará no lobby até que um usuário autenticado**.</span><span class="sxs-lookup"><span data-stu-id="947ab-117">In the **Conference bridge provider** pane, enable or disable **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="947ab-118">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="947ab-118">Click **Apply**.</span></span> 

<span data-ttu-id="947ab-119">**Usando o Skype para o Centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="947ab-119">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="947ab-120">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**.</span><span class="sxs-lookup"><span data-stu-id="947ab-120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="947ab-121">Na lista, selecione o usuário e no painel de ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="947ab-121">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="947ab-122">Na página de propriedades do usuário, em **Opções de reunião**, marque ou desmarque **chamadores de permitir não autenticado para ser as primeira pessoas em uma reunião. Se não, em seguida, eles aguardará no lobby até que um usuário autenticado**.</span><span class="sxs-lookup"><span data-stu-id="947ab-122">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="947ab-123">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="947ab-123">Click **Save**.</span></span> 
    
 <span data-ttu-id="947ab-124">**Usando o Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="947ab-124">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="947ab-125">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="947ab-125">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="947ab-126">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="947ab-126">What else should you know?</span></span>

- <span data-ttu-id="947ab-127">Se você quiser redefinir o PIN, consulte [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="947ab-127">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
- <span data-ttu-id="947ab-128">Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="947ab-128">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="947ab-129">Se a reunião ainda não iniciado (há ninguém na reunião ainda): um chamador será solicitado se ele for o organizador; Se ele diz Sim, ele será solicitado para seu PIN e depois que ele insere o PIN, iniciará a reunião e o usuário será ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="947ab-129">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="947ab-130">Se a reunião já iniciado (alguém já está na reunião): um chamador não será avisado se ele for o organizador, e ele nunca será solicitado para o PIN; a reunião já estará iniciada e o chamador participará.</span><span class="sxs-lookup"><span data-stu-id="947ab-130">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="947ab-131">Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, está desativado:</span><span class="sxs-lookup"><span data-stu-id="947ab-131">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="947ab-132">Se a reunião ainda não iniciado (há ninguém na reunião ainda): um chamador não será avisado se ela for o organizador, e ela nunca será solicitada para o PIN.</span><span class="sxs-lookup"><span data-stu-id="947ab-132">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="947ab-133">Como a configuração do organizador é definida como desativado, a reunião será iniciada e os chamadores anônimos serão ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="947ab-133">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="947ab-134">Se a reunião já iniciado (alguém já está na reunião): um chamador não será avisado se ela for o organizador, e ela nunca será solicitada para o PIN, a reunião já estará iniciada e o chamador participará.</span><span class="sxs-lookup"><span data-stu-id="947ab-134">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="947ab-135">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="947ab-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="947ab-136">Para economizar tempo e automatizar a tarefa para mais de um usuário, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="947ab-136">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="947ab-p104">No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="947ab-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="947ab-140">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="947ab-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="947ab-141">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="947ab-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="947ab-142">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="947ab-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="947ab-143">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="947ab-143">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="947ab-144">Introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="947ab-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="947ab-145">Como usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="947ab-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="947ab-146">Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="947ab-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="947ab-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="947ab-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="947ab-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="947ab-149">Related topics</span></span>

[<span data-ttu-id="947ab-150">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="947ab-150">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
