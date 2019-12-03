---
title: Teams para Infraestrutura de Área de Trabalho Virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: Saiba como executar o Microsoft Teams em um ambiente de infraestrutura de área de trabalho virtualizada (VDI).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdac909139a225d622098df5d7df44516edac7bd
ms.sourcegitcommit: 74c06b00ff78dc816a59e6c59e9be87181fc0f3e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39669239"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="c1996-103">Teams para Infraestrutura de Área de Trabalho Virtualizada</span><span class="sxs-lookup"><span data-stu-id="c1996-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="c1996-104">Este artigo descreve os requisitos e as limitações para usar o Microsoft Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="c1996-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="c1996-105">O que é VDI?</span><span class="sxs-lookup"><span data-stu-id="c1996-105">What is VDI?</span></span>

<span data-ttu-id="c1996-106">A Virtual Desktop Infrastructure (VDI) é a tecnologia de virtualização que hospeda um sistema operacional e aplicativos de área de trabalho em um servidor centralizado em um Data Center.</span><span class="sxs-lookup"><span data-stu-id="c1996-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="c1996-107">Isso permite uma experiência de área de trabalho totalmente personalizada para os usuários com uma fonte centralizada totalmente segura e compatível.</span><span class="sxs-lookup"><span data-stu-id="c1996-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="c1996-108">Atualmente, o Teams em um ambiente virtualizado está disponível com suporte para funcionalidade de colaboração e chat com uma máquina virtualizada (VM) persistente dedicada.</span><span class="sxs-lookup"><span data-stu-id="c1996-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="c1996-109">Para garantir uma experiência de usuário ideal, siga as orientações deste artigo.</span><span class="sxs-lookup"><span data-stu-id="c1996-109">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-requirements"></a><span data-ttu-id="c1996-110">Requisitos do teams</span><span class="sxs-lookup"><span data-stu-id="c1996-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="c1996-111">Definir políticas para desativar a funcionalidade de chamada e de reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="c1996-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="c1996-112">As chamadas e a experiência da reunião do Teams não são otimizadas para um ambiente VDI (disponível em breve).</span><span class="sxs-lookup"><span data-stu-id="c1996-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="c1996-113">Recomendamos que você defina políticas em nível de usuário para desativar a funcionalidade de chamada e reunião no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1996-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="c1996-114">Você ainda pode optar por executar o Teams totalmente na VDI usando o aplicativo da área de trabalho do teams ou o aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="c1996-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="c1996-115">No entanto, recomendamos que você defina as políticas para evitar comprometer a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="c1996-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>

<span data-ttu-id="c1996-116">Pode levar algum tempo (algumas horas) para que as alterações de política sejam propagadas.</span><span class="sxs-lookup"><span data-stu-id="c1996-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="c1996-117">Se você não vir as alterações de uma determinada conta imediatamente, tente novamente em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="c1996-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="c1996-118">Quando chamadas e reuniões de equipes são otimizadas para uso em ambientes de área de trabalho virtual, você pode reverter essas políticas e permitir que os usuários usem o Microsoft Teams normalmente.</span><span class="sxs-lookup"><span data-stu-id="c1996-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span>

#### <a name="calling"></a><span data-ttu-id="c1996-119">Chamadas</span><span class="sxs-lookup"><span data-stu-id="c1996-119">Calling</span></span>

<span data-ttu-id="c1996-120">Use os cmdlets **CSTeamsCallingPolicy** para controlar se os usuários podem usar as opções de chamadas e chamadas em conversas privadas e em grupo.</span><span class="sxs-lookup"><span data-stu-id="c1996-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="c1996-121">Veja a lista de configurações de política e os valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="c1996-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="c1996-122">Nome da política</span><span class="sxs-lookup"><span data-stu-id="c1996-122">Policy name</span></span>  |<span data-ttu-id="c1996-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="c1996-123">Description</span></span> |<span data-ttu-id="c1996-124">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="c1996-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c1996-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="c1996-125">AllowCalling</span></span>|<span data-ttu-id="c1996-126">Controla os recursos de chamada Interop.</span><span class="sxs-lookup"><span data-stu-id="c1996-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="c1996-127">Ativar isso permite que os usuários do Skype for Business tenham chamadas individuais com usuários do Microsoft Teams e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="c1996-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>|<span data-ttu-id="c1996-128">Definido como falso para impedir chamadas do pouso usuários do Skype for Business no Teams.</span><span class="sxs-lookup"><span data-stu-id="c1996-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>|
|<span data-ttu-id="c1996-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="c1996-129">AllowPrivateCalling</span></span>| <span data-ttu-id="c1996-130">Controla se o aplicativo de chamada está disponível na barra de aplicativos no lado esquerdo do cliente do Teams e se os usuários veem opções de chamadas e chamadas com vídeo em chat privado.</span><span class="sxs-lookup"><span data-stu-id="c1996-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat.</span></span> |<span data-ttu-id="c1996-131">Definido como falso para remover o aplicativo de chamada da barra de aplicativos no lado esquerdo do Teams e para remover as opções de chamadas e chamadas com vídeo no chat privado.</span><span class="sxs-lookup"><span data-stu-id="c1996-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>|

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="c1996-132">Criar e atribuir uma política de chamada</span><span class="sxs-lookup"><span data-stu-id="c1996-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="c1996-133">Inicie uma sessão do Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="c1996-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="c1996-134">Conecte-se ao conector online do Skype.</span><span class="sxs-lookup"><span data-stu-id="c1996-134">Connect to the Skype Online Connector.</span></span>

      ```powershell
      # Set Office 365 User Name and Password
      $username = "admin email address"
      password = ConvertTo-SecureString "password" -AsPlainText -Force
      $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
      # Connect to Skype Online
      Import-Module SkypeOnlineConnector
      $sfboSession = New-CsOnlineSession -Credential $LiveCred
      Import-PSSession $sfboSession
      ```

3. <span data-ttu-id="c1996-135">Exibir uma lista de opções de política de chamada.</span><span class="sxs-lookup"><span data-stu-id="c1996-135">View a list of calling policy options.</span></span>

      ```powershell
      Get-CsTeamsCallingPolicy
      ```

4. <span data-ttu-id="c1996-136">Procure a opção de política interna na qual todas as políticas de chamadas estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="c1996-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="c1996-137">Ele tem a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="c1996-137">It looks like this.</span></span>

        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="c1996-138">Aplique a opção de política interna do DisallowCalling a todos os usuários que usarão o Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="c1996-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

      ```powershell
      Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
      ```

<span data-ttu-id="c1996-139">Para obter mais informações sobre as políticas de chamada de equipes, consulte [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c1996-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="c1996-140">Reuniões</span><span class="sxs-lookup"><span data-stu-id="c1996-140">Meetings</span></span>

<span data-ttu-id="c1996-141">Use os cmdlets **CsTeamsMeetingPolicy** para controlar o tipo de reunião que os usuários podem criar, os recursos que eles podem acessar durante uma reunião e os recursos de reunião que estão disponíveis para usuários anônimos e externos.</span><span class="sxs-lookup"><span data-stu-id="c1996-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="c1996-142">Veja a lista de configurações de política e os valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="c1996-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="c1996-143">Nome da política</span><span class="sxs-lookup"><span data-stu-id="c1996-143">Policy Name</span></span> |<span data-ttu-id="c1996-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="c1996-144">Description</span></span>|<span data-ttu-id="c1996-145">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="c1996-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="c1996-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c1996-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="c1996-147">Determina se um usuário tem permissão para agendar reuniões particulares.</span><span class="sxs-lookup"><span data-stu-id="c1996-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="c1996-148">Defina como false para impedir que o usuário seja capaz de agendar reuniões particulares.</span><span class="sxs-lookup"><span data-stu-id="c1996-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span> |
|<span data-ttu-id="c1996-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="c1996-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="c1996-150">Determina se um usuário tem permissão para agendar reuniões de canal.</span><span class="sxs-lookup"><span data-stu-id="c1996-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="c1996-151">Defina como false para impedir que o usuário seja capaz de agendar reuniões de canal.</span><span class="sxs-lookup"><span data-stu-id="c1996-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>|
|<span data-ttu-id="c1996-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="c1996-152">AllowMeetNow</span></span> |<span data-ttu-id="c1996-153">Determina se um usuário tem permissão para criar ou iniciar reuniões ad hoc.</span><span class="sxs-lookup"><span data-stu-id="c1996-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span> | <span data-ttu-id="c1996-154">Defina como false para impedir que o usuário seja capaz de iniciar reuniões ad hoc.</span><span class="sxs-lookup"><span data-stu-id="c1996-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span> |
|<span data-ttu-id="c1996-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="c1996-155">ScreenSharingMode</span></span> | <span data-ttu-id="c1996-156">Determina o modo no qual um usuário pode compartilhar sua tela em chamadas ou reuniões.</span><span class="sxs-lookup"><span data-stu-id="c1996-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="c1996-157">Definido como desabilitado para proibir o usuário de compartilhar suas telas.</span><span class="sxs-lookup"><span data-stu-id="c1996-157">Set to Disabled to prohibit the user from sharing their screens.</span></span> |
|<span data-ttu-id="c1996-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="c1996-158">AllowIPVideo</span></span> |<span data-ttu-id="c1996-159">Determina se o vídeo está habilitado em reuniões ou chamadas de um usuário.</span><span class="sxs-lookup"><span data-stu-id="c1996-159">Determines whether video is enabled in a user's meetings or calls.</span></span> | <span data-ttu-id="c1996-160">Defina como false para impedir que o usuário Compartilhe seu vídeo.</span><span class="sxs-lookup"><span data-stu-id="c1996-160">Set to False to prohibit the user from sharing their video.</span></span> |
| <span data-ttu-id="c1996-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="c1996-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="c1996-162">Determina se os usuários anônimos podem discar para um número PSTN.</span><span class="sxs-lookup"><span data-stu-id="c1996-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="c1996-163">Defina como falso para proibir usuários anônimos de discar.</span><span class="sxs-lookup"><span data-stu-id="c1996-163">Set to False to prohibit anonymous users from dialing out.</span></span> |
| <span data-ttu-id="c1996-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="c1996-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="c1996-165">Determina se os usuários anônimos podem iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-165">Determines whether anonymous users can start a meeting.</span></span> | <span data-ttu-id="c1996-166">Defina como false para impedir que os usuários iniciem uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-166">Set to False to prohibit users from starting a meeting.</span></span> |
| <span data-ttu-id="c1996-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="c1996-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="c1996-168">Determina se um usuário pode agendar reuniões de equipes no cliente da área de trabalho do Outlook.</span><span class="sxs-lookup"><span data-stu-id="c1996-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span> | <span data-ttu-id="c1996-169">Defina como false para proibir um usuário de agendar reuniões do teams no cliente da área de trabalho do Outlook.</span><span class="sxs-lookup"><span data-stu-id="c1996-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client.</span></span> |
| <span data-ttu-id="c1996-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="c1996-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="c1996-171">Determina se os participantes podem solicitar ou dar controle ao compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="c1996-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="c1996-172">Definido como false para impedir que o usuário dê e solicite o controle em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-172">Set to False to prohibit the user from giving and requesting control in a meeting.</span></span> |
| <span data-ttu-id="c1996-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="c1996-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="c1996-174">Determina se os participantes externos podem solicitar ou dar controle ao compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="c1996-174">Determines whether external participants can request or give control of screen sharing.</span></span> | <span data-ttu-id="c1996-175">Defina como false para impedir que um usuário externo dê, solicitando o controle em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-175">Set to False to prohibit an external user from giving, requesting control in a meeting.</span></span> |
| <span data-ttu-id="c1996-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="c1996-176">AllowPowerPointSharing</span></span> |<span data-ttu-id="c1996-177">Determina se o compartilhamento do PowerPoint é permitido em reuniões de um usuário.</span><span class="sxs-lookup"><span data-stu-id="c1996-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="c1996-178">Defina como false para impedir que um usuário Compartilhe arquivos do PowerPoint em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting.</span></span> |
| <span data-ttu-id="c1996-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="c1996-179">AllowWhiteboard</span></span> | <span data-ttu-id="c1996-180">Determina se o whiteboard é permitido em reuniões de um usuário.</span><span class="sxs-lookup"><span data-stu-id="c1996-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> | <span data-ttu-id="c1996-181">Defina como false para proibir o quadro de comunicações em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-181">Set to False to prohibit whiteboard in a meeting.</span></span> |
| <span data-ttu-id="c1996-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="c1996-182">AllowTranscription</span></span> |<span data-ttu-id="c1996-183">Determina se as transcrições e as legendas de tempo real e/ou pós-reunião são permitidas nas reuniões de um usuário.</span><span class="sxs-lookup"><span data-stu-id="c1996-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span> | <span data-ttu-id="c1996-184">Defina como falso para proibir transcrição e legendas em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-184">Set to False to prohibit transcription and captions in a meeting.</span></span> |
| <span data-ttu-id="c1996-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="c1996-185">AllowSharedNotes</span></span> | <span data-ttu-id="c1996-186">Determina se os usuários têm permissão para fazer anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="c1996-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="c1996-187">Defina como falso para proibir os usuários de fazer anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="c1996-187">Set to False to prohibit users from taking shared notes.</span></span> |
| <span data-ttu-id="c1996-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="c1996-188">MediaBitRateKB</span></span> |<span data-ttu-id="c1996-189">Determina a taxa de bits de mídia para transmissões de compartilhamento de áudio/vídeo/aplicativo em reuniões.</span><span class="sxs-lookup"><span data-stu-id="c1996-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings.</span></span> | <span data-ttu-id="c1996-190">O valor sugerido é 5000 (5 MB).</span><span class="sxs-lookup"><span data-stu-id="c1996-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="c1996-191">Você pode alterá-lo com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1996-191">You can change it based on your organization’s needs.</span></span> |

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="c1996-192">Criar e atribuir uma política de reunião</span><span class="sxs-lookup"><span data-stu-id="c1996-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="c1996-193">Inicie uma sessão do Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="c1996-193">Start a Windows PowerShell session as an administrator.</span></span>
1. <span data-ttu-id="c1996-194">Conecte-se ao conector online do Skype.</span><span class="sxs-lookup"><span data-stu-id="c1996-194">Connect to the Skype Online Connector.</span></span>

      ```powershell
      # Set Office 365 User Name and Password
      $username = "admin email address"
      password = ConvertTo-SecureString "password" -AsPlainText -Force
      $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
      # Connect to Skype Online
      Import-Module SkypeOnlineConnector
      $sfboSession = New-CsOnlineSession -Credential $LiveCred
      Import-PSSession $sfboSession
      ```

1. <span data-ttu-id="c1996-195">Exibir uma lista de opções de política de reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-195">View a list of meeting policy options.</span></span>

      ```powershell
      Get-CsTeamsMeetingPolicy
      ```

1. <span data-ttu-id="c1996-196">Procure a opção de política interna na qual todas as políticas de reunião estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="c1996-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="c1996-197">Ele tem a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="c1996-197">It looks like this.</span></span>

        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

1. <span data-ttu-id="c1996-198">Aplique a opção de política interna do AllOff a todos os usuários que usarão o Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="c1996-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

      ```powershell
      Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
      ```

 <span data-ttu-id="c1996-199">Para obter mais informações sobre as políticas de reunião do Teams, consulte [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="c1996-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="c1996-200">Requisitos do provedor de virtualização</span><span class="sxs-lookup"><span data-stu-id="c1996-200">Virtualization provider requirements</span></span>

<span data-ttu-id="c1996-201">O aplicativo Teams foi validado nos principais provedores de soluções de virtualização.</span><span class="sxs-lookup"><span data-stu-id="c1996-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="c1996-202">Com vários provedores de mercado, consulte seu provedor de soluções de virtualização para garantir que os requisitos mínimos sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="c1996-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="c1996-203">Requisitos da máquina virtual</span><span class="sxs-lookup"><span data-stu-id="c1996-203">Virtual Machine requirements</span></span>

> [!NOTE]
> <span data-ttu-id="c1996-204">Os seguintes requisitos se aplicam ao aplicativo da área de trabalho Teams e ao aplicativo Web Teams.</span><span class="sxs-lookup"><span data-stu-id="c1996-204">The following requirements apply to both the Teams desktop app and the Teams Web app.</span></span>

<span data-ttu-id="c1996-205">Com as diversas cargas de trabalho e necessidades de usuário em um ambiente virtualizado, a seguir está a configuração de VM mínima recomendada.</span><span class="sxs-lookup"><span data-stu-id="c1996-205">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="c1996-206">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="c1996-206">Parameter</span></span> |<span data-ttu-id="c1996-207">Certa</span><span class="sxs-lookup"><span data-stu-id="c1996-207">Measure</span></span> |
|---------|---------|
|<span data-ttu-id="c1996-208">vCPU</span><span class="sxs-lookup"><span data-stu-id="c1996-208">vCPU</span></span> | <span data-ttu-id="c1996-209">2 núcleos</span><span class="sxs-lookup"><span data-stu-id="c1996-209">2 cores</span></span> |
|<span data-ttu-id="c1996-210">RAM</span><span class="sxs-lookup"><span data-stu-id="c1996-210">RAM</span></span> | <span data-ttu-id="c1996-211">4 GB</span><span class="sxs-lookup"><span data-stu-id="c1996-211">4 GB</span></span> |
|<span data-ttu-id="c1996-212">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="c1996-212">Storage</span></span> | <span data-ttu-id="c1996-213">8 GB</span><span class="sxs-lookup"><span data-stu-id="c1996-213">8 GB</span></span> |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="c1996-214">Requisitos do sistema operacional da máquina virtual</span><span class="sxs-lookup"><span data-stu-id="c1996-214">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="c1996-215">Os sistemas operacionais com suporte para VM são:</span><span class="sxs-lookup"><span data-stu-id="c1996-215">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="c1996-216">Windows 10 e posterior</span><span class="sxs-lookup"><span data-stu-id="c1996-216">Windows 10 and later</span></span>
- <span data-ttu-id="c1996-217">Windows Server 2012 R2 e posterior</span><span class="sxs-lookup"><span data-stu-id="c1996-217">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="c1996-218">Instalar o Microsoft Teams no VDI</span><span class="sxs-lookup"><span data-stu-id="c1996-218">Install Teams on VDI</span></span>

<span data-ttu-id="c1996-219">Aqui está o processo e as ferramentas para implantar o aplicativo da área de trabalho Teams.</span><span class="sxs-lookup"><span data-stu-id="c1996-219">Here's the process and tools to deploy the Teams desktop app.</span></span>

1. <span data-ttu-id="c1996-220">Baixe o pacote MSI do Teams usando um dos seguintes links, dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1996-220">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="c1996-221">Recomendamos a versão de 64 bits de uma máquina virtual (VM) da VDI com um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c1996-221">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="c1996-222">Versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="c1996-222">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="c1996-223">Versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="c1996-223">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

1. <span data-ttu-id="c1996-224">Execute o seguinte comando para instalar o MSI na VM da VDI (ou conclua a atualização).</span><span class="sxs-lookup"><span data-stu-id="c1996-224">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

      ```
      msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
      ```

    <span data-ttu-id="c1996-225">Isso instala o Teams em Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="c1996-225">This installs Teams to Program Files.</span></span> <span data-ttu-id="c1996-226">Nesse ponto, a configuração da imagem dourada está concluída.</span><span class="sxs-lookup"><span data-stu-id="c1996-226">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="c1996-227">A próxima sessão de logon interativo inicia o Teams e pede credenciais.</span><span class="sxs-lookup"><span data-stu-id="c1996-227">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="c1996-228">Lembre-se de que não é possível desativar o início automático do Teams ao instalá-lo na VDI usando a propriedade ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="c1996-228">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

1. <span data-ttu-id="c1996-229">Execute o comando a seguir para desinstalar o MSI na VM da VDI (ou preparar para atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="c1996-229">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

      ```
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

    <span data-ttu-id="c1996-230">Isso desinstala o Teams do Arquivos de Programas.</span><span class="sxs-lookup"><span data-stu-id="c1996-230">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="c1996-231">Limitações e problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="c1996-231">Known issues and limitations</span></span>

<span data-ttu-id="c1996-232">Os itens a seguir são limitações e problemas conhecidos do teams em VDI.</span><span class="sxs-lookup"><span data-stu-id="c1996-232">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="c1996-233">**Implantações de tipos de host de sessão compartilhada**: implantações de tipo de host de sessão compartilhada (por exemplo, configuração de VM não persistente compartilhada) não estão no escopo.</span><span class="sxs-lookup"><span data-stu-id="c1996-233">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="c1996-234">**Chamadas e reuniões**:</span><span class="sxs-lookup"><span data-stu-id="c1996-234">**Calling and meetings**:</span></span>

  - <span data-ttu-id="c1996-235">Os cenários de chamada e reunião não são otimizados para VDI.</span><span class="sxs-lookup"><span data-stu-id="c1996-235">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="c1996-236">Esses cenários serão executados com baixa qualidade.</span><span class="sxs-lookup"><span data-stu-id="c1996-236">These scenarios will perform poorly.</span></span> <span data-ttu-id="c1996-237">Recomendamos o uso de políticas em nível de usuário, conforme descrito na seção [definir as políticas para desativar a funcionalidade de chamada e de reunião na seção Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="c1996-237">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
  - <span data-ttu-id="c1996-238">A aplicação das políticas descritas neste artigo impacta a capacidade de usar a funcionalidade de chamada e de reunião, o que, dependendo das outras políticas, pode afetar outros usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="c1996-238">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="c1996-239">Se os usuários da sua organização usarem clientes não VDI, você poderá optar por não aplicar as políticas.</span><span class="sxs-lookup"><span data-stu-id="c1996-239">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="c1996-240">**Ingressando em chamadas e reuniões criadas por outros usuários**: embora as políticas impeçam que os usuários criem reuniões, elas ainda podem ingressar em reuniões se outro usuário discar para elas pela reunião.</span><span class="sxs-lookup"><span data-stu-id="c1996-240">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="c1996-241">Nessas reuniões, a capacidade do usuário de compartilhar vídeo, usar o whiteboard e outros recursos depende se você desabilitou esses recursos usando o TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="c1996-241">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>

- <span data-ttu-id="c1996-242">**Conteúdo em cache**: se o ambiente virtual no qual as equipes estiver em execução não for persistente (e os dados forem limpos no final de cada sessão do usuário), os usuários poderão observar a degradação do desempenho devido à atualização de conteúdo, independentemente de o usuário ter acesso ao mesmo conteúdo em uma sessão anterior.</span><span class="sxs-lookup"><span data-stu-id="c1996-242">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>

- <span data-ttu-id="c1996-243">**Atualizações do cliente**: o Teams no VDI não é atualizado automaticamente com a instalação MSI por computador.</span><span class="sxs-lookup"><span data-stu-id="c1996-243">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="c1996-244">Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção instalar o Microsoft [Teams no VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="c1996-244">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="c1996-245">Você deve desinstalar a versão atual para atualizar para uma versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="c1996-245">You must uninstall the current version to update to a newer version.</span></span>

- <span data-ttu-id="c1996-246">**Experiência do usuário**: a experiência do usuário do teams em um ambiente VDI pode ser diferente de um ambiente não VDI.</span><span class="sxs-lookup"><span data-stu-id="c1996-246">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="c1996-247">As diferenças podem ser devido às configurações de política e/ou suporte a recursos no ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1996-247">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="c1996-248">Para os problemas conhecidos do teams que não estão relacionados ao VDI, consulte [problemas conhecidos do Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c1996-248">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c1996-249">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c1996-249">Related topics</span></span>

- [<span data-ttu-id="c1996-250">Instalar o Microsoft Teams usando MSI</span><span class="sxs-lookup"><span data-stu-id="c1996-250">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
