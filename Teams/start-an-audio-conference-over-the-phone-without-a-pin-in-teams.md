---
title: Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Saiba como habilitar ou desabilitar chamadores anônimos para participar de uma reunião no centro de administração do Teams. '
ms.openlocfilehash: 87588bc8edfcc4d50b5589339f92f56829ec38ef
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837911"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="1776a-103">Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1776a-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="1776a-104">Para os usuários que discarem para uma reunião, pode ser frustrante ficar no lobby ouvindo música porque um organizador do Microsoft Teams não iniciou a reunião.</span><span class="sxs-lookup"><span data-stu-id="1776a-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="1776a-105">Por padrão, se o organizador de uma reunião faz uma chamada de entrada para a reunião, é necessário um PIN para iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="1776a-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="1776a-106">É possível configurar a reunião para que qualquer pessoa possa discar para uma reunião e não ser solicitado a digitar um PIN para iniciá-la.</span><span class="sxs-lookup"><span data-stu-id="1776a-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="1776a-107">É possível usar o centro de administração para ativar ou desativar essa configuração para um único usuário.</span><span class="sxs-lookup"><span data-stu-id="1776a-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="1776a-108">Não é obrigatório um PIN para o organizador da reunião se alguém tiver iniciado a reunião a partir do aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1776a-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="1776a-109">É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="1776a-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="1776a-110">O PIN da reunião é enviado para o usuário de áudio quando a licença de **Audioconferência** é atribuída a ele ou quando ele é habilitado para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="1776a-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="1776a-111">Consulte[Enviar um e-mail para um usuário com as informações de audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) e[E-mails enviados automaticamente para os usuários quando as configurações de audioconferência são alteradas](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1776a-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="1776a-112">Habilitar ou desabilitar chamadores anônimos para participar de uma reunião</span><span class="sxs-lookup"><span data-stu-id="1776a-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="1776a-113">![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="1776a-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1776a-114">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="1776a-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="1776a-115">Selecione um usuário na lista e clique em **Editar** no topo da página.</span><span class="sxs-lookup"><span data-stu-id="1776a-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="1776a-116">Próximo a **Audioconferência**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1776a-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="1776a-117">No painel **conferência de áudio** , habilite ou desabilite **chamadores de discagem podem ser a primeira pessoa em uma reunião**.</span><span class="sxs-lookup"><span data-stu-id="1776a-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="1776a-118">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="1776a-118">Click **Apply**.</span></span> 

<span data-ttu-id="1776a-119">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1776a-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="1776a-120">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1776a-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="1776a-121">O que mais você precisa saber?</span><span class="sxs-lookup"><span data-stu-id="1776a-121">What else should you know?</span></span>

- <span data-ttu-id="1776a-122">Se desejar redefinir o PIN, veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1776a-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="1776a-123">Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião estiver desabilitado:</span><span class="sxs-lookup"><span data-stu-id="1776a-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="1776a-124">Se a reunião não tiver sido iniciada (ainda não tem ninguém na reunião): será perguntado ao chamador se ele é o organizador; se responder que sim, ele será solicitado a inserir o PIN. Depois que o PIN for inserido, a reunião será iniciada e o usuário entrará na reunião.</span><span class="sxs-lookup"><span data-stu-id="1776a-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="1776a-125">Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.</span><span class="sxs-lookup"><span data-stu-id="1776a-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="1776a-126">Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="1776a-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="1776a-127">Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN.</span><span class="sxs-lookup"><span data-stu-id="1776a-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="1776a-128">Como a configuração do organizador está definida como desativada, a reunião será iniciada e os chamadores anônimos poderão entrar na reunião.</span><span class="sxs-lookup"><span data-stu-id="1776a-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="1776a-129">Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.</span><span class="sxs-lookup"><span data-stu-id="1776a-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1776a-130">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1776a-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="1776a-p104">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1776a-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1776a-134">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="1776a-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1776a-135">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1776a-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="1776a-136">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1776a-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1776a-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1776a-137">Related topics</span></span>

[<span data-ttu-id="1776a-138">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="1776a-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
