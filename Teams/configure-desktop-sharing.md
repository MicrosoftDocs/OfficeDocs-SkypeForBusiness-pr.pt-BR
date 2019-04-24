---
title: Configurar o compartilhamento de área de trabalho no Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurar uma política de reunião para permitir que os usuários compartilhem suas áreas de trabalho em chats de equipes ou em reuniões
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0434804e7d0ec57ff4470fd8e9af23b73f8179f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198378"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="1514c-103">Configurar o compartilhamento de área de trabalho no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1514c-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="1514c-104">Compartilhamento da área de trabalho permite que os usuários apresentar uma tela ou app durante uma reunião ou bate-papo.</span><span class="sxs-lookup"><span data-stu-id="1514c-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="1514c-105">Os administradores podem configurar Teams da Microsoft para permitir que usuários compartilhar uma tela inteira, um aplicativo ou um arquivo de compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="1514c-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="1514c-106">Você pode permitir que usuários conceder ou solicitar o controle, permitir o compartilhamento do PowerPoint, adicione um quadro de comunicações e permitir anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="1514c-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="1514c-107">Você também pode configurar se os usuários anônimos ou externos podem solicitar o controle da tela compartilhada.</span><span class="sxs-lookup"><span data-stu-id="1514c-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="1514c-108">Para configurar o compartilhamento de tela, você pode cria uma nova política de reuniões e atribuí-la para os usuários que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="1514c-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="1514c-109">**No Centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="1514c-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1514c-110">Selecione **reuniões** > **políticas de reunião**.</span><span class="sxs-lookup"><span data-stu-id="1514c-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Selecione políticas de reunião](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="1514c-112">Na página de **políticas de reunião** , selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="1514c-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Selecione nova política](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="1514c-114">Dê um título exclusivo de sua política e insira uma breve descrição.</span><span class="sxs-lookup"><span data-stu-id="1514c-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="1514c-115">Em **compartilhamento de conteúdo**, escolha um **modo de compartilhamento de tela** da lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="1514c-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="1514c-116">**Tela inteira** – permite que os usuários compartilhar sua área de trabalho inteira.</span><span class="sxs-lookup"><span data-stu-id="1514c-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="1514c-117">**Único aplicativo** – permite que os usuários compartilhamento de tela do limite a um único aplicativo ativo.</span><span class="sxs-lookup"><span data-stu-id="1514c-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="1514c-118">**Desabilitado** – desativa o compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="1514c-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Escolha uma modo de compartilhamento de tela](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="1514c-120">Ative ou desativar o as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="1514c-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="1514c-121">**Permitir que um participante dar ou solicitar o controle** – permite que membros da equipe de conceder ou solicitar o controle da área de trabalho do apresentador ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1514c-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="1514c-122">**Permitir que um participante externo dar ou solicitar o controle** – permite convidados e usuários (federados) externos dar ou solicitar o controle da área de trabalho ou do aplicativo do apresentador.</span><span class="sxs-lookup"><span data-stu-id="1514c-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="1514c-123">**Compartilhamento de PowerPoint permitir** - permite aos usuários criar reuniões que permitem apresentações do PowerPoint sejam carregados e compartilhados.</span><span class="sxs-lookup"><span data-stu-id="1514c-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="1514c-124">**Quadro de comunicações permitir** – permite que os usuários compartilhem um quadro de comunicações.</span><span class="sxs-lookup"><span data-stu-id="1514c-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="1514c-125">**Permitir anotações compartilhadas** – permite que os usuários façam anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="1514c-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="1514c-126">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1514c-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="1514c-127">Usar o PowerShell para configurar a área de trabalho compartilhada</span><span class="sxs-lookup"><span data-stu-id="1514c-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="1514c-128">Você também pode usar o cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar o compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1514c-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="1514c-129">Defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1514c-129">Set the following parameters:</span></span>

- <span data-ttu-id="1514c-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="1514c-130">Description</span></span>
- <span data-ttu-id="1514c-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="1514c-131">ScreenSharingMode</span></span>
- <span data-ttu-id="1514c-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="1514c-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="1514c-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="1514c-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="1514c-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="1514c-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="1514c-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="1514c-135">AllowWhiteboard</span></span>
- <span data-ttu-id="1514c-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="1514c-136">AllowSharedNotes</span></span>

<span data-ttu-id="1514c-137">[Saiba mais sobre como usar o cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1514c-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

