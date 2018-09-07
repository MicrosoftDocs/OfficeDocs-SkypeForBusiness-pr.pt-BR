---
title: Iniciar uma conferência de áudio por telefone sem um PIN em Teams da Microsoft
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a habilitar ou desabilitar os chamadores anônimos ingressem em uma reunião a partir do Centro de administração do equipes. '
ms.openlocfilehash: f85cd3e2ae0c1f87810f5b5312ba8bc9dc9d34c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861039"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="bf1df-103">Iniciar uma conferência de áudio por telefone sem um PIN em Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf1df-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="bf1df-104">Talvez seja frustrante para usuários que discam para uma reunião para ser mantidos no lobby da reunião escutando música porque o organizador da reunião Teams da Microsoft não tiver iniciado a reunião.</span><span class="sxs-lookup"><span data-stu-id="bf1df-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="bf1df-105">Se o organizador da reunião chama reunião, por padrão, é necessário um PIN para iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="bf1df-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="bf1df-106">Você pode montá-lo para que qualquer pessoa pode discar para uma reunião e não ser solicitado a fornecer um PIN para iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="bf1df-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="bf1df-107">Você pode usar o Centro de administração para habilitar ou desabilitar essa configuração de um único usuário.</span><span class="sxs-lookup"><span data-stu-id="bf1df-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="bf1df-108">Um PIN não é necessário para o organizador da reunião, se alguém tiver iniciado a reunião do Microsoft Teams app.</span><span class="sxs-lookup"><span data-stu-id="bf1df-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="bf1df-109">É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="bf1df-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="bf1df-110">O PIN para reuniões é enviado ao usuário áudio quando eles recebem a licença de **Serviços de audioconferência** e estão habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="bf1df-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="bf1df-111">Consulte [Enviar um email a um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) e [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bf1df-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="bf1df-112">Habilitar ou desabilitar chamadores anônimos para participar de uma reunião</span><span class="sxs-lookup"><span data-stu-id="bf1df-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="bf1df-113">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="bf1df-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bf1df-114">No painel de navegação esquerdo, clique em **usuários**.</span><span class="sxs-lookup"><span data-stu-id="bf1df-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="bf1df-115">Selecione um usuário na lista e clique em **Editar** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="bf1df-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="bf1df-116">Ao lado de **Conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bf1df-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="bf1df-117">No painel de **Conferência de áudio** , habilitar ou desabilitar **os chamadores não-autenticados podem ser a primeira pessoa em uma reunião**.</span><span class="sxs-lookup"><span data-stu-id="bf1df-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="bf1df-118">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bf1df-118">Click **Save**.</span></span> 

<span data-ttu-id="bf1df-119">**Usando o Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="bf1df-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="bf1df-120">Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bf1df-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="bf1df-121">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="bf1df-121">What else should you know?</span></span>

- <span data-ttu-id="bf1df-122">Se você deseja redefinir o PIN, consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bf1df-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="bf1df-123">Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="bf1df-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="bf1df-124">Se a reunião ainda não iniciado (há ninguém na reunião ainda): um chamador será solicitado se ele for o organizador; Se ele diz Sim, ele será solicitado para seu PIN e depois que ele insere o PIN, iniciará a reunião e o usuário será ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="bf1df-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="bf1df-125">Se a reunião já iniciado (alguém já está na reunião): um chamador não será avisado se ele for o organizador, e ele nunca será solicitado para o PIN; a reunião já estará iniciada e o chamador participará.</span><span class="sxs-lookup"><span data-stu-id="bf1df-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="bf1df-126">Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, está desativado:</span><span class="sxs-lookup"><span data-stu-id="bf1df-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="bf1df-127">Se a reunião ainda não iniciado (há ninguém na reunião ainda): um chamador não será avisado se ela for o organizador, e ela nunca será solicitada para o PIN.</span><span class="sxs-lookup"><span data-stu-id="bf1df-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="bf1df-128">Como a configuração do organizador é definida como desativado, a reunião será iniciada e os chamadores anônimos serão ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="bf1df-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="bf1df-129">Se a reunião já iniciado (alguém já está na reunião): um chamador não será avisado se ela for o organizador, e ela nunca será solicitada para o PIN, a reunião já estará iniciada e o chamador participará.</span><span class="sxs-lookup"><span data-stu-id="bf1df-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bf1df-130">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bf1df-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bf1df-p104">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="bf1df-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bf1df-134">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="bf1df-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bf1df-135">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf1df-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bf1df-136">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bf1df-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bf1df-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bf1df-137">Related topics</span></span>

[<span data-ttu-id="bf1df-138">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="bf1df-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
