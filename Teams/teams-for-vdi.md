---
title: Equipes de infraestrutura de área de trabalho virtualizada
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Saiba como executar Teams da Microsoft em um ambiente virtualizado do Desktop Infrastructure (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869826"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="cc365-103">Equipes de infraestrutura de área de trabalho virtualizada</span><span class="sxs-lookup"><span data-stu-id="cc365-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="cc365-104">Este artigo descreve os requisitos e limitações para usar o Microsoft Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="cc365-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="cc365-105">O que é VDI?</span><span class="sxs-lookup"><span data-stu-id="cc365-105">What is VDI?</span></span>

<span data-ttu-id="cc365-106">Virtual Desktop Infrastructure (VDI) é uma tecnologia de virtualização que hospeda um sistema operacional de área de trabalho e aplicativos em um servidor centralizado em um data center.</span><span class="sxs-lookup"><span data-stu-id="cc365-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="cc365-107">Isso permite uma experiência de área de trabalho totalmente personalizada para usuários com uma fonte centralizada totalmente protegido e em conformidade.</span><span class="sxs-lookup"><span data-stu-id="cc365-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="cc365-108">Atualmente, equipes em um ambiente virtualizado está disponível com suporte para a funcionalidade de bate-papo e colaboração com uma dedicado persistente virtualizada VM (máquina).</span><span class="sxs-lookup"><span data-stu-id="cc365-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="cc365-109">Para garantir uma experiência ideal do usuário, siga as orientações neste artigo.</span><span class="sxs-lookup"><span data-stu-id="cc365-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="cc365-110">Requisitos de equipes</span><span class="sxs-lookup"><span data-stu-id="cc365-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="cc365-111">Definir diretivas para desativar a chamada e funcionalidade nas equipes de reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="cc365-112">As equipes chamando-se e experiência de reunião não está otimizado para um ambiente de VDI (em breve).</span><span class="sxs-lookup"><span data-stu-id="cc365-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="cc365-113">Recomendamos que você defina políticas no nível do usuário para desativar, chamando-se e funcionalidade nas equipes de reunião.</span><span class="sxs-lookup"><span data-stu-id="cc365-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="cc365-114">Você ainda pode optar por executar as equipes de totalmente em VDI usando o aplicativo de área de trabalho de equipes ou aplicativo da web.</span><span class="sxs-lookup"><span data-stu-id="cc365-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="cc365-115">No entanto, recomendamos que você defina as políticas para evitar comprometer a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="cc365-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="cc365-116">Pode levar algum tempo (algumas horas) para que as alterações de diretiva propagar.</span><span class="sxs-lookup"><span data-stu-id="cc365-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="cc365-117">Se você não vir as alterações de uma determinada conta imediatamente, tente novamente em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="cc365-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="cc365-118">Quando a chamada de equipes e reuniões são otimizados para uso em ambientes virtuais de área de trabalho, você pode reverter essas políticas e permitir que usuários usem equipes como faria normalmente.</span><span class="sxs-lookup"><span data-stu-id="cc365-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="cc365-119">Chamadas</span><span class="sxs-lookup"><span data-stu-id="cc365-119">Calling</span></span>

<span data-ttu-id="cc365-120">Use os cmdlets de **CSTeamsCallingPolicy** para controlar se os usuários poderão usar chamando-se e opções de chamada em particular e chats de grupo.</span><span class="sxs-lookup"><span data-stu-id="cc365-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="cc365-121">Aqui está uma lista de configurações de diretiva e valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="cc365-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="cc365-122">Nome da política</span><span class="sxs-lookup"><span data-stu-id="cc365-122">Policy name</span></span>  |<span data-ttu-id="cc365-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc365-123">Description</span></span> |<span data-ttu-id="cc365-124">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="cc365-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cc365-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="cc365-125">AllowCalling</span></span>    |<span data-ttu-id="cc365-126">Interoperabilidade de controles recursos de chamada.</span><span class="sxs-lookup"><span data-stu-id="cc365-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="cc365-127">Ativando Isso permite Skype para que os usuários corporativos pessoal durante chamadas com usuários de equipes e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="cc365-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="cc365-128">Defina como False para evitar que as chamadas para usuários comerciais inicial em equipes do Skype.</span><span class="sxs-lookup"><span data-stu-id="cc365-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="cc365-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="cc365-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="cc365-130">Controla se o aplicativo de chamada está disponível na barra de aplicativos no lado esquerdo do cliente equipes e se os usuários veem a chamada e opções de chamada no bate-papo privado de vídeo</span><span class="sxs-lookup"><span data-stu-id="cc365-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="cc365-131">Defina como False para remover o aplicativo de chamada da barra de aplicativos no lado esquerdo de equipes e remover as opções de chamada de chamada e vídeo no bate-papo privado.</span><span class="sxs-lookup"><span data-stu-id="cc365-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="cc365-132">Criar e atribuir uma política de chamada</span><span class="sxs-lookup"><span data-stu-id="cc365-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="cc365-133">Inicie uma sessão do Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="cc365-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="cc365-134">Conecte-se ao conector Skype Online.</span><span class="sxs-lookup"><span data-stu-id="cc365-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="cc365-135">Exiba uma lista de opções de política de chamada.</span><span class="sxs-lookup"><span data-stu-id="cc365-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="cc365-136">Procure a opção de diretiva interna onde todas as diretivas de chamada estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="cc365-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="cc365-137">Ele tem esta aparência.</span><span class="sxs-lookup"><span data-stu-id="cc365-137">It looks like this.</span></span>
   
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

5. <span data-ttu-id="cc365-138">Aplique a opção de diretiva interna de DisallowCalling a todos os usuários que usarão as equipes em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="cc365-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="cc365-139">Para obter mais informações sobre políticas de chamada de equipes, consulte [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="cc365-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="cc365-140">Reuniões</span><span class="sxs-lookup"><span data-stu-id="cc365-140">Meetings</span></span>

<span data-ttu-id="cc365-141">Use os cmdlets **CsTeamsMeetingPolicy** para controlar o tipo de reuniões que os usuários podem criar, os recursos que eles possam acessar enquanto estiver em uma reunião e os recursos da reunião que estão disponíveis para usuários anônimos e externos.</span><span class="sxs-lookup"><span data-stu-id="cc365-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="cc365-142">Aqui está uma lista de configurações de diretiva e valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="cc365-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="cc365-143">Nome da política</span><span class="sxs-lookup"><span data-stu-id="cc365-143">Policy Name</span></span> |<span data-ttu-id="cc365-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="cc365-144">Description</span></span>|<span data-ttu-id="cc365-145">Valor recomendado</span><span class="sxs-lookup"><span data-stu-id="cc365-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="cc365-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="cc365-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="cc365-147">Determina se um usuário tem permissão para agendar reuniões privadas.</span><span class="sxs-lookup"><span data-stu-id="cc365-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="cc365-148">Defina como False para proibir que o usuário poder agendar reuniões privadas.</span><span class="sxs-lookup"><span data-stu-id="cc365-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="cc365-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="cc365-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="cc365-150">Determina se um usuário tem permissão para agendar reuniões de canal.</span><span class="sxs-lookup"><span data-stu-id="cc365-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="cc365-151">Defina como False para proibir que o usuário poder agendar reuniões de canal.</span><span class="sxs-lookup"><span data-stu-id="cc365-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="cc365-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="cc365-152">AllowMeetNow</span></span> |<span data-ttu-id="cc365-153">Determina se um usuário tem permissão para criar ou iniciar reuniões ad hoc.</span><span class="sxs-lookup"><span data-stu-id="cc365-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="cc365-154">Defini-la como False para proibir que o usuário poder iniciar reuniões ad hoc.</span><span class="sxs-lookup"><span data-stu-id="cc365-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="cc365-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="cc365-155">ScreenSharingMode</span></span> | <span data-ttu-id="cc365-156">Determina o modo em que um usuário tem permissão para compartilhar sua tela em chamadas ou reuniões.</span><span class="sxs-lookup"><span data-stu-id="cc365-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="cc365-157">Defina como desabilitado para impedir que o usuário de suas telas de compartilhamento</span><span class="sxs-lookup"><span data-stu-id="cc365-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="cc365-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="cc365-158">AllowIPVideo</span></span> |<span data-ttu-id="cc365-159">Determina se o vídeo é habilitado em reuniões ou chamadas de um usuário.</span><span class="sxs-lookup"><span data-stu-id="cc365-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="cc365-160">Defina como False para proibir que o usuário compartilhando sua vídeo</span><span class="sxs-lookup"><span data-stu-id="cc365-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="cc365-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="cc365-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="cc365-162">Determina se os usuários anônimos poderão discar para um número PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc365-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="cc365-163">Defina como False para proibir que os usuários anônimos discagem externa</span><span class="sxs-lookup"><span data-stu-id="cc365-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="cc365-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="cc365-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="cc365-165">Determina se os usuários anônimos podem iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="cc365-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="cc365-166">Defina como False para proibir que os usuários iniciando uma reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="cc365-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="cc365-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="cc365-168">Determina se um usuário pode agendar reuniões de equipes no cliente de desktop do Outlook.</span><span class="sxs-lookup"><span data-stu-id="cc365-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="cc365-169">Defina como False para proibir que um usuário agendar reuniões de equipes no cliente de desktop do Outlook</span><span class="sxs-lookup"><span data-stu-id="cc365-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="cc365-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="cc365-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="cc365-171">Determina se os participantes podem solicitar ou conceder o controle de compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="cc365-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="cc365-172">Defina como False para proibir que o usuário oferecendo e solicitar controle em uma reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="cc365-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="cc365-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="cc365-174">Determina se os participantes externos podem solicitar ou conceder o controle de compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="cc365-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="cc365-175">Defina como False para proibir que um usuário externo oferecendo, solicitando o controle em uma reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="cc365-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="cc365-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="cc365-177">Determina se o compartilhamento do PowerPoint é permitida em reuniões de um usuário.</span><span class="sxs-lookup"><span data-stu-id="cc365-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="cc365-178">Defina como False para proibir que um usuário compartilhando arquivos do PowerPoint em uma reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="cc365-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="cc365-179">AllowWhiteboard</span></span> | <span data-ttu-id="cc365-180">Determina se o quadro de comunicações é permitido em reuniões de um usuário.</span><span class="sxs-lookup"><span data-stu-id="cc365-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="cc365-181">Defina como False para proibir o quadro de comunicações em uma reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="cc365-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="cc365-182">AllowTranscription</span></span> |<span data-ttu-id="cc365-183">Determina se as legendas em tempo real e/ou posteriores à reunião e transcrições são permitidas em reuniões de um usuário.</span><span class="sxs-lookup"><span data-stu-id="cc365-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="cc365-184">Defina como False para proibir transcrição e legendas em uma reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="cc365-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="cc365-185">AllowSharedNotes</span></span> | <span data-ttu-id="cc365-186">Determina se os usuários poderão fazer anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="cc365-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="cc365-187">Defina como False para proibir que os usuários fazer anotações compartilhadas</span><span class="sxs-lookup"><span data-stu-id="cc365-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="cc365-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="cc365-188">MediaBitRateKB</span></span> |<span data-ttu-id="cc365-189">Determina a taxa de bits de mídia de áudio/vídeo/app compartilhamento transmissões em reuniões</span><span class="sxs-lookup"><span data-stu-id="cc365-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="cc365-190">Valor sugerido é 5000 (5 MB).</span><span class="sxs-lookup"><span data-stu-id="cc365-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="cc365-191">Você pode alterar, com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cc365-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="cc365-192">Criar e atribuir uma política de reunião</span><span class="sxs-lookup"><span data-stu-id="cc365-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="cc365-193">Inicie uma sessão do Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="cc365-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="cc365-194">Conecte-se ao conector Skype Online.</span><span class="sxs-lookup"><span data-stu-id="cc365-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="cc365-195">Exiba uma lista de opções de política de reunião.</span><span class="sxs-lookup"><span data-stu-id="cc365-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="cc365-196">Procure a opção de diretiva interna onde todas as políticas de reunião estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="cc365-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="cc365-197">Ele tem esta aparência.</span><span class="sxs-lookup"><span data-stu-id="cc365-197">It looks like this.</span></span>
   
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

5. <span data-ttu-id="cc365-198">Aplique a opção de diretiva interna de AllOff a todos os usuários que usarão as equipes em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="cc365-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="cc365-199">Para obter mais informações sobre políticas de reunião de equipes, consulte [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="cc365-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="cc365-200">Requisitos do provedor de virtualização</span><span class="sxs-lookup"><span data-stu-id="cc365-200">Virtualization provider requirements</span></span>

<span data-ttu-id="cc365-201">O aplicativo de equipes foi validado no principais provedores de solução de virtualização.</span><span class="sxs-lookup"><span data-stu-id="cc365-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="cc365-202">Com vários provedores de mercado, consulte seu provedor de soluções de virtualização para garantir que sejam cumpridos os requisitos mínimos.</span><span class="sxs-lookup"><span data-stu-id="cc365-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="cc365-203">Requisitos de máquina virtual</span><span class="sxs-lookup"><span data-stu-id="cc365-203">Virtual Machine requirements</span></span>

<span data-ttu-id="cc365-204">Com as cargas de trabalho diversas e as necessidades do usuário em um ambiente virtualizado, a seguir é o mínimo recomendado de configuração da VM.</span><span class="sxs-lookup"><span data-stu-id="cc365-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="cc365-205">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="cc365-205">Parameter</span></span>  |<span data-ttu-id="cc365-206">Medida</span><span class="sxs-lookup"><span data-stu-id="cc365-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="cc365-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="cc365-207">vCPU</span></span>    |  <span data-ttu-id="cc365-208">2 núcleos</span><span class="sxs-lookup"><span data-stu-id="cc365-208">2 cores</span></span>       |
|<span data-ttu-id="cc365-209">RAM</span><span class="sxs-lookup"><span data-stu-id="cc365-209">RAM</span></span>     |  <span data-ttu-id="cc365-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="cc365-210">4 GB</span></span>      |
|<span data-ttu-id="cc365-211">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="cc365-211">Storage</span></span>     | <span data-ttu-id="cc365-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="cc365-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="cc365-213">Requisitos de sistema operacional da máquina virtual</span><span class="sxs-lookup"><span data-stu-id="cc365-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="cc365-214">Os sistemas operacionais suportados para a VM são:</span><span class="sxs-lookup"><span data-stu-id="cc365-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="cc365-215">Windows 10 e posterior</span><span class="sxs-lookup"><span data-stu-id="cc365-215">Windows 10 and later</span></span>
- <span data-ttu-id="cc365-216">Windows Server 2012 R2 e posterior</span><span class="sxs-lookup"><span data-stu-id="cc365-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="cc365-217">Instalar equipes em VDI</span><span class="sxs-lookup"><span data-stu-id="cc365-217">Install Teams on VDI</span></span>

<span data-ttu-id="cc365-218">Aqui está o processo e ferramentas para implantar o aplicativo de área de trabalho de equipes.</span><span class="sxs-lookup"><span data-stu-id="cc365-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="cc365-219">Baixe o pacote MSI equipes usando um dos links a seguir, dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="cc365-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="cc365-220">Recomendamos a versão de 64 bits para uma VM VDI com um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="cc365-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="cc365-221">versão de 32 bits</span><span class="sxs-lookup"><span data-stu-id="cc365-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="cc365-222">versão de 64 bits</span><span class="sxs-lookup"><span data-stu-id="cc365-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="cc365-223">Execute o seguinte comando para instalar o MSI do VM VDI (ou concluir atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="cc365-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="cc365-224">Essa etapa instala equipes para arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="cc365-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="cc365-225">Neste ponto, a configuração de imagem de ouro estará concluída.</span><span class="sxs-lookup"><span data-stu-id="cc365-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="cc365-226">A próxima sessão de logon interativo inicia equipes e solicita credenciais.</span><span class="sxs-lookup"><span data-stu-id="cc365-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="cc365-227">Observe que não é possível desabilitar a inicialização automática das equipes ao instalar equipes em VDI usando a propriedade ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="cc365-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="cc365-228">Execute o seguinte comando para desinstalar o MSI de VDI VM (ou se preparar para atualizá-lo).</span><span class="sxs-lookup"><span data-stu-id="cc365-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="cc365-229">Isso desinstala equipes de arquivos de programa.</span><span class="sxs-lookup"><span data-stu-id="cc365-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="cc365-230">Problemas e limitações conhecidos</span><span class="sxs-lookup"><span data-stu-id="cc365-230">Known issues and limitations</span></span>

<span data-ttu-id="cc365-231">A seguir está problemas conhecida e limitações para equipes de VDI.</span><span class="sxs-lookup"><span data-stu-id="cc365-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="cc365-232">**Implantações de tipo de host de sessão compartilhados**: implantações de tipo de host de sessão de compartilhados (por exemplo, não é persistente VM configuração compartilhada) não estão em escopo.</span><span class="sxs-lookup"><span data-stu-id="cc365-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="cc365-233">A **chamada e reuniões**:</span><span class="sxs-lookup"><span data-stu-id="cc365-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="cc365-234">Chamada e cenários de reunião não são otimizados para VDI.</span><span class="sxs-lookup"><span data-stu-id="cc365-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="cc365-235">Esses cenários executará mal.</span><span class="sxs-lookup"><span data-stu-id="cc365-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="cc365-236">É recomendável usar políticas de nível de usuário, conforme descrito na seção [definir diretivas para desativar o chamando-se e funcionalidade nas equipes de reunião](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="cc365-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="cc365-237">Aplicar as políticas descritas neste artigo afeta a capacidade de usar a funcionalidade de reunião e de chamada, que, dependendo das outras políticas, pode afetar outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cc365-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="cc365-238">Se os usuários em sua organização usarem os clientes não-VDI, você pode optar por não aplicar as políticas.</span><span class="sxs-lookup"><span data-stu-id="cc365-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="cc365-239">**Ingressando em chamadas e reuniões criados por outros usuários**: Embora as políticas de restringem os usuários da criação de reuniões, eles ainda podem ingressar em reuniões se outro usuário discar para acessá-los da reunião.</span><span class="sxs-lookup"><span data-stu-id="cc365-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="cc365-240">Nessas reuniões, a capacidade do usuário para compartilhar vídeo, usar quadro de comunicações e outros recursos dependem se você desabilitou esses recursos usando TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="cc365-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="cc365-241">**Cache de conteúdo**: se for o ambiente virtual no quais as equipes de execução não é persistente (e dados limpos no final de cada sessão do usuário), os usuários podem observar a diminuição do desempenho devido à atualização de conteúdo, independentemente se o usuário acessada a mesma conteúdo em uma sessão anterior.</span><span class="sxs-lookup"><span data-stu-id="cc365-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="cc365-242">**Atualizações do cliente**: equipes de VDI não é atualizado automaticamente como a forma como os clientes não - VDI equipes estão.</span><span class="sxs-lookup"><span data-stu-id="cc365-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="cc365-243">Você precisa atualizar a imagem da VM instalando um novo MSI, conforme descrito na seção [Instalar equipes em VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="cc365-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="cc365-244">Você deve desinstalar a versão atual para atualizar para uma versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="cc365-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="cc365-245">**Experiência do usuário**: equipes a experiência do usuário em um ambiente VDI pode ser diferente de um ambiente de não-VDI.</span><span class="sxs-lookup"><span data-stu-id="cc365-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="cc365-246">As diferenças podem ser devido às configurações de política e/ou o recurso de suporte no ambiente.</span><span class="sxs-lookup"><span data-stu-id="cc365-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="cc365-247">Para as equipes problemas conhecidos que não estão relacionados ao VDI, consulte [problemas para equipes da Microsoft conhecidos](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cc365-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc365-248">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cc365-248">Related topics</span></span>

- [<span data-ttu-id="cc365-249">Instalar usando o MSI Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="cc365-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)