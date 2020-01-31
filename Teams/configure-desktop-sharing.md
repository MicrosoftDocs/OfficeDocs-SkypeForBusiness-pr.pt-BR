---
title: Configurar o compartilhamento de área de trabalho no Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Configurar uma política de reunião para permitir que os usuários compartilhem suas áreas de trabalho nos chats ou reuniões do teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb3340da960728b1a261efc510573702c5a17076
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628707"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="cad5f-103">Configurar o compartilhamento de área de trabalho no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cad5f-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="cad5f-104">O compartilhamento de área de trabalho permite que os usuários apresentem uma tela ou um aplicativo durante uma reunião ou chat.</span><span class="sxs-lookup"><span data-stu-id="cad5f-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="cad5f-105">Os administradores podem configurar o compartilhamento de tela no Microsoft Teams para permitir que os usuários compartilhem uma tela inteira, um aplicativo ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="cad5f-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="cad5f-106">Você pode permitir que os usuários forneçam ou solicitem controle, permitam o compartilhamento do PowerPoint, adicionem um quadro de comunicações e permitam anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="cad5f-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="cad5f-107">Você também pode configurar se usuários anônimos ou externos podem solicitar o controle da tela compartilhada.</span><span class="sxs-lookup"><span data-stu-id="cad5f-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="cad5f-108">Para configurar o compartilhamento de tela, crie uma nova política de reuniões e atribua-a aos usuários que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="cad5f-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="cad5f-109">**No [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="cad5f-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="cad5f-110">Selecionar \*\*\*\* > **as políticas de reunião**de reuniões.</span><span class="sxs-lookup"><span data-stu-id="cad5f-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Captura de tela mostrando as políticas de reunião selecionadas](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="cad5f-112">Na página **políticas de reunião** , selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="cad5f-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Captura de tela mostrando a mensagem de políticas de reunião](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="cad5f-114">Dê à sua política um título exclusivo e insira uma breve descrição.</span><span class="sxs-lookup"><span data-stu-id="cad5f-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="cad5f-115">Em **compartilhamento de conteúdo**, escolha um **modo de compartilhamento de tela** na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="cad5f-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="cad5f-116">**Tela inteira** – permite que os usuários compartilhem toda a área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cad5f-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="cad5f-117">**Aplicativo único** – permite que os usuários limitem o compartilhamento de tela a um único aplicativo ativo.</span><span class="sxs-lookup"><span data-stu-id="cad5f-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="cad5f-118">**Desabilitado** – desativa o compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="cad5f-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Captura de tela mostrando as opções do modo de compartilhamento](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="cad5f-120">Ativar ou desativar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="cad5f-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="cad5f-121">**Permitir que um participante conceda ou solicite o controle** – permite que os membros da equipe conceda ou solicitem o controle da área de trabalho ou do aplicativo do apresentador.</span><span class="sxs-lookup"><span data-stu-id="cad5f-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="cad5f-122">**Permitir que um participante externo conceda ou solicite controle** – permite que convidados e usuários externos (federados) conceda ou solicitem controle da área de trabalho ou do aplicativo do apresentador.</span><span class="sxs-lookup"><span data-stu-id="cad5f-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="cad5f-123">**Permitir compartilhamento do PowerPoint** -permite que os usuários criem reuniões que permitem que as apresentações do PowerPoint sejam carregadas e compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="cad5f-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="cad5f-124">**Permitir quadro de comunicações** – permite que os usuários compartilhem um quadro de comunicações.</span><span class="sxs-lookup"><span data-stu-id="cad5f-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="cad5f-125">**Permitir anotações compartilhadas** – permite que os usuários façam anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="cad5f-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="cad5f-126">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cad5f-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="cad5f-127">Usar o PowerShell para configurar a área de trabalho compartilhada</span><span class="sxs-lookup"><span data-stu-id="cad5f-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="cad5f-128">Você também pode usar o cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar o compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cad5f-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="cad5f-129">Defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="cad5f-129">Set the following parameters:</span></span>

- <span data-ttu-id="cad5f-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="cad5f-130">Description</span></span>
- <span data-ttu-id="cad5f-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="cad5f-131">ScreenSharingMode</span></span>
- <span data-ttu-id="cad5f-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="cad5f-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="cad5f-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="cad5f-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="cad5f-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="cad5f-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="cad5f-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="cad5f-135">AllowWhiteboard</span></span>
- <span data-ttu-id="cad5f-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="cad5f-136">AllowSharedNotes</span></span>

<span data-ttu-id="cad5f-137">[Saiba mais sobre como usar o cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cad5f-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

