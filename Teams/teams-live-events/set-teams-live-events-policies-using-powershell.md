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
description: Exemplos de como usar o PowerShell para definir políticas em equipes para controlar quem pode conter eventos ao vivo na sua organização e os recursos que estão disponíveis nos eventos que eles criam
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23cf75c8e764920a2d77c3bbe6c0cb3711c22f04
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459624"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="cd102-103">Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd102-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="cd102-104">Você pode usar os seguintes cmdlets do Windows PowerShell para definir e atribuir configurações de diretiva para eventos ao vivo em equipes:</span><span class="sxs-lookup"><span data-stu-id="cd102-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="cd102-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cd102-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="cd102-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cd102-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="cd102-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cd102-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="cd102-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cd102-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="cd102-109">Eis alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="cd102-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="cd102-110">Permitir que os usuários agendem eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="cd102-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="cd102-111">Esses exemplos são para eventos de início rápido.</span><span class="sxs-lookup"><span data-stu-id="cd102-111">These examples are for quick start events.</span></span> <span data-ttu-id="cd102-112">Para eventos externos codificador, há etapas adicionais que você deve fazer.</span><span class="sxs-lookup"><span data-stu-id="cd102-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="cd102-113">Para obter mais informações, consulte [habilitar usuários agendar a eventos externos codificador](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span><span class="sxs-lookup"><span data-stu-id="cd102-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="cd102-114">**Permitir que um usuário agendar eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="cd102-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="cd102-115">Se o usuário é atribuído a política global, execute e verificar se o parâmetro *AllowBroadcastScheduling* está definido como *True*:</span><span class="sxs-lookup"><span data-stu-id="cd102-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="cd102-116">Atribua o usuário para a política global, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="cd102-117">Cenários de usuário</span><span class="sxs-lookup"><span data-stu-id="cd102-117">User scenarios</span></span>
<span data-ttu-id="cd102-118">**Você deseja que todos os usuários em sua organização possam agendar eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="cd102-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="cd102-119">Se os usuários são atribuídos a política global, execute e confirme que *AllowBroadcastScheduling* \* estiver definida como *True*:</span><span class="sxs-lookup"><span data-stu-id="cd102-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="cd102-120">Se os usuários são atribuídos a uma política que não seja a política global, execute e verificar se a opção *-AllowBroadcastScheduling* está definida como *True*:</span><span class="sxs-lookup"><span data-stu-id="cd102-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="cd102-121">**Você deseja agendar a ser desabilitado em toda a organização de eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="cd102-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="cd102-122">Desabilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="cd102-123">Atribua a todos os usuários em sua organização para a política global, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="cd102-124">**Você deseja um grande número de usuários possam agendar eventos ao vivo e impedir que um conjunto de usuários agendamento-los**</span><span class="sxs-lookup"><span data-stu-id="cd102-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="cd102-125">Execute e verificar se *AllowBroadcastScheduling* está definida como *True*:</span><span class="sxs-lookup"><span data-stu-id="cd102-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="cd102-126">Em seguida, atribua um ou mais usuários para a política global, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="cd102-127">Crie uma nova política que não permite agendar eventos ao vivo, executados:</span><span class="sxs-lookup"><span data-stu-id="cd102-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="cd102-128">Desabilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="cd102-129">Atribua usuários a essa diretiva, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="cd102-130">**Você deseja desabilitar o agendamento para um grande número de usuários de evento ao vivo e permitir que um conjunto de usuários para agendá-las**</span><span class="sxs-lookup"><span data-stu-id="cd102-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="cd102-131">Desabilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="cd102-132">Em seguida, atribua esses usuários para a política global, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="cd102-133">Crie uma diretiva para permitir o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="cd102-134">Habilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="cd102-135">Atribua usuários a essa diretiva, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="cd102-136">Definir quem pode ingressar eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="cd102-136">Set who can join live events</span></span>
 
<span data-ttu-id="cd102-137">Defina a política global que permite aos usuários criar eventos que todos, inclusive usuários anônimos, que pode participar, execute:</span><span class="sxs-lookup"><span data-stu-id="cd102-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="cd102-138">Definir a opção de gravação para eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="cd102-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="cd102-139">Essa configuração se aplica apenas a eventos de início rápido.</span><span class="sxs-lookup"><span data-stu-id="cd102-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="cd102-140">Defina a política global para desabilitar o registro de eventos ao vivo:</span><span class="sxs-lookup"><span data-stu-id="cd102-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="cd102-141">Definir a transcrição e uma tradução em eventos ao vivo (em breve)</span><span class="sxs-lookup"><span data-stu-id="cd102-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="cd102-142">Essa configuração se aplica apenas a eventos de início rápido.</span><span class="sxs-lookup"><span data-stu-id="cd102-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="cd102-143">Defina a política global para ativar na transcrição e uma tradução para os participantes do evento:</span><span class="sxs-lookup"><span data-stu-id="cd102-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="cd102-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cd102-144">Related topics</span></span>
- [<span data-ttu-id="cd102-145">Configurar para equipes eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="cd102-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


