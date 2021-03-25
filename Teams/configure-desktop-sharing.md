---
title: Configurar o compartilhamento da área de trabalho no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como configurar uma política de reunião para permitir que os usuários compartilhem suas áreas de trabalho em chats ou reuniões do Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56ee2c83827c25da5b16cc3f7c2725a3daf815c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121509"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="7e474-103">Configurar o compartilhamento da área de trabalho no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e474-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="7e474-104">O compartilhamento da área de trabalho permite que os usuários apresentem uma tela ou aplicativo durante uma reunião ou bate-papo.</span><span class="sxs-lookup"><span data-stu-id="7e474-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="7e474-105">Os administradores podem configurar o compartilhamento de tela no Microsoft Teams para permitir que os usuários compartilhem uma tela inteira, um aplicativo ou um arquivo.</span><span class="sxs-lookup"><span data-stu-id="7e474-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="7e474-106">Você pode permitir que os usuários deem ou solicitem controle, permitam o compartilhamento do PowerPoint, adicionem um quadro branco e permitam anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="7e474-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="7e474-107">Você também pode configurar se usuários anônimos ou externos podem solicitar o controle da tela compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7e474-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="7e474-108">Os participantes externos nas reuniões das Teams podem ser categorizados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7e474-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="7e474-109">Usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="7e474-109">Anonymous user</span></span>
- <span data-ttu-id="7e474-110">Usuários convidados</span><span class="sxs-lookup"><span data-stu-id="7e474-110">Guest users</span></span>
- <span data-ttu-id="7e474-111">Usuário B2B</span><span class="sxs-lookup"><span data-stu-id="7e474-111">B2B user</span></span>
- <span data-ttu-id="7e474-112">Usuário federado</span><span class="sxs-lookup"><span data-stu-id="7e474-112">Federated user</span></span>

<span data-ttu-id="7e474-113">Para configurar o compartilhamento de tela, crie uma nova política de reuniões e a atribua aos usuários que quer gerenciar.</span><span class="sxs-lookup"><span data-stu-id="7e474-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="7e474-114">**No [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="7e474-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="7e474-115">Clique em **Reuniões** > **Políticas de reuniões**.</span><span class="sxs-lookup"><span data-stu-id="7e474-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![Políticas de reunião selecionadas](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="7e474-117">Na página **Políticas de reunião,** selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7e474-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![A mensagem Políticas de reunião](media/addMeeting.png)

3. <span data-ttu-id="7e474-119">Atribua um título exclusivo à sua política e insira uma breve descrição.</span><span class="sxs-lookup"><span data-stu-id="7e474-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="7e474-120">Em **Compartilhamento de conteúdo**, escolha um **Modo de compartilhamento de tela** da lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="7e474-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="7e474-121">**Tela inteira** – permite que os usuários compartilhem toda a área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7e474-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="7e474-122">**Aplicativo único** – permite que os usuários limitem o compartilhamento de tela a um único aplicativo ativo.</span><span class="sxs-lookup"><span data-stu-id="7e474-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="7e474-123">**Desabilitado** – desativa o compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="7e474-123">**Disabled** – Turns off screen sharing.</span></span>

    ![As opções de modo de compartilhamento](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="7e474-125">Você não precisa habilitar a política de chamada para que os usuários usem o compartilhamento de tela do chat.</span><span class="sxs-lookup"><span data-stu-id="7e474-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="7e474-126">No entanto, o áudio deles é desligado até que eles mesmos se desmuterem.</span><span class="sxs-lookup"><span data-stu-id="7e474-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="7e474-127">Além disso, o usuário que compartilha a tela pode clicar em **Adicionar Áudio** para habilitar o áudio.</span><span class="sxs-lookup"><span data-stu-id="7e474-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="7e474-128">Se a política de chamada estiver desabilitada, os usuários não poderão adicionar áudio ao compartilhamento de tela de uma sessão de chat.</span><span class="sxs-lookup"><span data-stu-id="7e474-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="7e474-129">Ative ou desative as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7e474-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="7e474-130">**Permitir que um participante dê ou solicite** controle – permite que os membros da equipe dêm ou solicitem controle da área de trabalho ou do aplicativo do apresentador.</span><span class="sxs-lookup"><span data-stu-id="7e474-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="7e474-131">**Permitir que um participante externo dê ou solicite controle** – essa é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="7e474-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="7e474-132">Se uma organização tiver esse conjunto para um usuário, não controla o que os participantes externos podem fazer, independentemente do que o organizador da reunião definiu.</span><span class="sxs-lookup"><span data-stu-id="7e474-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="7e474-133">Esse parâmetro controla se os participantes externos podem receber ou solicitar controle da tela de compartilhamento do participante, dependendo do que o participante do compartilhamento definiu dentro das políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7e474-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="7e474-134">**Permitir o compartilhamento do PowerPoint** - permite que os usuários criem reuniões que permitem que as apresentações do PowerPoint sejam carregadas e compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="7e474-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="7e474-135">**Permitir quadro de comunicações** – permite que os usuários compartilhem um quadro de comunicações.</span><span class="sxs-lookup"><span data-stu-id="7e474-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="7e474-136">**Permitir anotações compartilhadas** – permite que os usuários façam anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="7e474-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="7e474-137">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7e474-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="7e474-138">Use o PowerShell para configurar a área de trabalho compartilhada</span><span class="sxs-lookup"><span data-stu-id="7e474-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="7e474-139">Você também pode usar o cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar o compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7e474-139">You can also use the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="7e474-140">Use os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="7e474-140">Set the following parameters:</span></span>

- <span data-ttu-id="7e474-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="7e474-141">Description</span></span>
- <span data-ttu-id="7e474-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="7e474-142">ScreenSharingMode</span></span>
- <span data-ttu-id="7e474-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="7e474-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="7e474-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="7e474-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="7e474-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="7e474-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="7e474-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="7e474-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="7e474-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="7e474-147">AllowWhiteboard</span></span>
- <span data-ttu-id="7e474-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="7e474-148">AllowSharedNotes</span></span>

<span data-ttu-id="7e474-149">[Saiba mais sobre como usar o cmdlet csTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7e474-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>