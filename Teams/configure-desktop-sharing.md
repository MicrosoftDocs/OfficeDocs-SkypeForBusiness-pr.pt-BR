---
title: Configurar o compartilhamento da área de trabalho no Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como configurar uma política de reunião para permitir que os usuários compartilhem suas áreas de trabalho nos chats ou reuniões do teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34d7780e1d10370b78c11c1a8021381aff71f479
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552587"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="6f77b-103">Configurar o compartilhamento da área de trabalho no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f77b-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="6f77b-104">O compartilhamento da área de trabalho permite que os usuários apresentem uma tela ou aplicativo durante uma reunião ou bate-papo.</span><span class="sxs-lookup"><span data-stu-id="6f77b-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="6f77b-105">Os administradores podem configurar o compartilhamento de tela no Microsoft Teams para permitir que os usuários compartilhem uma tela inteira, um aplicativo ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="6f77b-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="6f77b-106">Você pode permitir que os usuários deem ou solicitem controle, permitam o compartilhamento do PowerPoint, adicionem um quadro branco e permitam anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="6f77b-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="6f77b-107">Você também pode configurar se usuários anônimos ou externos podem solicitar o controle da tela compartilhada.</span><span class="sxs-lookup"><span data-stu-id="6f77b-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="6f77b-108">Para configurar o compartilhamento de tela, crie uma nova política de reuniões e a atribua aos usuários que quer gerenciar.</span><span class="sxs-lookup"><span data-stu-id="6f77b-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="6f77b-109">**No [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="6f77b-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="6f77b-110">Clique em **Reuniões** > **Políticas de reuniões**.</span><span class="sxs-lookup"><span data-stu-id="6f77b-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Captura de tela exibindo as políticas das reuniões selecionadas](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="6f77b-112">Na página **Políticas de reunião**, clique em **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="6f77b-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Captura de tela exibindo a mensagem das políticas de reunião](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="6f77b-114">Atribua um título exclusivo à sua política e insira uma breve descrição.</span><span class="sxs-lookup"><span data-stu-id="6f77b-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="6f77b-115">Em **Compartilhamento de conteúdo**, escolha um **Modo de compartilhamento de tela** da lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="6f77b-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="6f77b-116">**Tela inteira** – permite que os usuários compartilhem toda a área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6f77b-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="6f77b-117">**Aplicativo único** – permite que os usuários limitem o compartilhamento de tela a um único aplicativo ativo.</span><span class="sxs-lookup"><span data-stu-id="6f77b-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="6f77b-118">**Desabilitado** – desativa o compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="6f77b-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Captura de tela exibindo as opções do modo de compartilhamento](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="6f77b-120">Ative ou desative as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="6f77b-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="6f77b-121">**Permitir que um participante conceda ou solicite o controle** – permite que os membros da equipe conceda ou solicitem o controle da área de trabalho ou do aplicativo do apresentador.</span><span class="sxs-lookup"><span data-stu-id="6f77b-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="6f77b-122">**Permitir que um participante externo conceda ou solicite o controle** – essa é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="6f77b-122">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="6f77b-123">Não importa se uma organização tem essa definição para um usuário não controla o que os participantes externos podem fazer, independentemente do que o organizador da reunião definiu.</span><span class="sxs-lookup"><span data-stu-id="6f77b-123">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="6f77b-124">Esse parâmetro controla se os participantes externos podem receber controle ou solicitação de controle da tela do participante do compartilhamento, dependendo do que o participante do compartilhamento definiu nas políticas de reunião da organização.</span><span class="sxs-lookup"><span data-stu-id="6f77b-124">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="6f77b-125">**Permitir o compartilhamento do PowerPoint** - permite que os usuários criem reuniões que permitem que as apresentações do PowerPoint sejam carregadas e compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="6f77b-125">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="6f77b-126">**Permitir quadro de comunicações** – permite que os usuários compartilhem um quadro de comunicações.</span><span class="sxs-lookup"><span data-stu-id="6f77b-126">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="6f77b-127">**Permitir anotações compartilhadas** – permite que os usuários façam anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="6f77b-127">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="6f77b-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6f77b-128">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="6f77b-129">Use o PowerShell para configurar a área de trabalho compartilhada</span><span class="sxs-lookup"><span data-stu-id="6f77b-129">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="6f77b-130">Você também pode usar o cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar o compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6f77b-130">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="6f77b-131">Use os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6f77b-131">Set the following parameters:</span></span>

- <span data-ttu-id="6f77b-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="6f77b-132">Description</span></span>
- <span data-ttu-id="6f77b-133">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="6f77b-133">ScreenSharingMode</span></span>
- <span data-ttu-id="6f77b-134">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="6f77b-134">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="6f77b-135">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="6f77b-135">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="6f77b-136">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="6f77b-136">AllowPowerPointSharing</span></span>
- <span data-ttu-id="6f77b-137">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="6f77b-137">AllowWhiteboard</span></span>
- <span data-ttu-id="6f77b-138">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="6f77b-138">AllowSharedNotes</span></span>

<span data-ttu-id="6f77b-139">[Saiba mais sobre como usar o cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6f77b-139">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

