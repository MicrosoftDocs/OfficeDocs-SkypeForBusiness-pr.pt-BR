---
title: Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Exemplos de como usar o PowerShell para definir políticas nas equipes controlar quem pode armazenar eventos dinâmicos em sua organização e recursos que estão disponíveis nos eventos que eles criam
appliesto:
- Microsoft Teams
ms.openlocfilehash: f92541cfdb69237631d1552202e95e4843987a30
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2019
ms.locfileid: "35012970"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="c0575-103">Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0575-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="c0575-104">Você pode usar os seguintes cmdlets do Windows PowerShell para definir e atribuir configurações de política para eventos dinâmicos no Teams:</span><span class="sxs-lookup"><span data-stu-id="c0575-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="c0575-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c0575-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c0575-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c0575-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c0575-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c0575-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c0575-108">Grant CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c0575-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="c0575-109">Veja alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="c0575-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="c0575-110">Permitir que os usuários agendem eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="c0575-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="c0575-111">Esses exemplos são para eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="c0575-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="c0575-112">Para eventos produzidos com um aplicativo ou dispositivo externo, há etapas adicionais que você deve fazer.</span><span class="sxs-lookup"><span data-stu-id="c0575-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="c0575-113">Para obter mais informações, consulte [habilitar usuários para agendar eventos que foram produzidos com um aplicativo ou dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="c0575-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="c0575-114">**Permitir que um usuário agende eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="c0575-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="c0575-115">Se o usuário tiver atribuído a política global, execute e verifique se o parâmetro *AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="c0575-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c0575-116">Em seguida, atribua o usuário à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="c0575-117">Cenários de usuário</span><span class="sxs-lookup"><span data-stu-id="c0575-117">User scenarios</span></span>
<span data-ttu-id="c0575-118">**Você quer que todos os usuários da sua organização possam agendar eventos dinâmicos**</span><span class="sxs-lookup"><span data-stu-id="c0575-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="c0575-119">Se os usuários tiverem atribuído a política global, execute e verifique se *AllowBroadcastScheduling* \* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="c0575-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c0575-120">Se os usuários receberem uma política diferente da política global, execute e verifique se *-AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="c0575-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="c0575-121">**Você deseja que o agendamento de eventos dinâmicos seja desabilitado em toda a sua organização**</span><span class="sxs-lookup"><span data-stu-id="c0575-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="c0575-122">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c0575-123">Atribuir todos os usuários de sua organização à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c0575-124">**Você quer que um grande número de usuários possa agendar eventos dinâmicos e impedir que um conjunto de usuários o agende**</span><span class="sxs-lookup"><span data-stu-id="c0575-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="c0575-125">Execute e verifique se o *AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="c0575-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="c0575-126">Em seguida, atribua um usuário ou usuários à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c0575-127">Criar uma nova política que não permita eventos dinâmicos de agendamento, execute:</span><span class="sxs-lookup"><span data-stu-id="c0575-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="c0575-128">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="c0575-129">Em seguida, atribua usuários a essa política, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="c0575-130">**Você deseja desabilitar o agendamento de eventos dinâmicos para um grande número de usuários e permitir que um conjunto de usuários os agende**</span><span class="sxs-lookup"><span data-stu-id="c0575-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="c0575-131">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c0575-132">Em seguida, atribua a esses usuários a política global, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="c0575-133">Criar uma política para permitir agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="c0575-134">Habilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="c0575-135">Em seguida, atribua usuários a essa política, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="c0575-136">Definir quem pode participar de eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="c0575-136">Set who can join live events</span></span>
 
<span data-ttu-id="c0575-137">Defina a política global para permitir que os usuários criem eventos que todos, incluindo usuários anônimos, possam participar, executar:</span><span class="sxs-lookup"><span data-stu-id="c0575-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="c0575-138">Definir a opção de gravação para eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="c0575-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="c0575-139">Essa configuração se aplica somente a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="c0575-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="c0575-140">Defina a política global para desabilitar a gravação de eventos dinâmicos:</span><span class="sxs-lookup"><span data-stu-id="c0575-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="c0575-141">Definir transcrição e tradução em eventos dinâmicos (em breve)</span><span class="sxs-lookup"><span data-stu-id="c0575-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="c0575-142">Essa configuração se aplica somente a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="c0575-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="c0575-143">Defina a política global para ativar a transcrição e a tradução para os participantes do evento:</span><span class="sxs-lookup"><span data-stu-id="c0575-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="c0575-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c0575-144">Related topics</span></span>
- [<span data-ttu-id="c0575-145">Configurar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="c0575-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


