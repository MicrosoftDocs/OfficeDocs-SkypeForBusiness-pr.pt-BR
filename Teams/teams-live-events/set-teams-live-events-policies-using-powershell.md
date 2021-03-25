---
title: Usar o PowerShell para definir políticas de eventos ao vivo
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Exemplos de como usar o PowerShell para definir políticas no Teams para controlar quem pode realizar eventos ao vivo em sua organização e os recursos disponíveis nos eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119140"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="8726c-103">Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8726c-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="8726c-104">Você pode usar os seguintes cmdlets Windows PowerShell para definir e atribuir configurações de política para eventos ao vivo no Teams:</span><span class="sxs-lookup"><span data-stu-id="8726c-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="8726c-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="8726c-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="8726c-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="8726c-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="8726c-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="8726c-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="8726c-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="8726c-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="8726c-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="8726c-109">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="8726c-110">Aqui estão alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="8726c-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="8726c-111">Antes de executar esses cmdlets, você deve estar conectado ao PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="8726c-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="8726c-112">Para obter mais informações, consulte [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="8726c-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="8726c-113">Permitir que os usuários agendem eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="8726c-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="8726c-114">Esses exemplos são para eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="8726c-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="8726c-115">Para eventos produzidos com um aplicativo ou dispositivo externo, há etapas adicionais que você deve fazer.</span><span class="sxs-lookup"><span data-stu-id="8726c-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="8726c-116">Para obter mais informações, consulte Permitir que os usuários [agendem eventos que foram produzidos com um aplicativo ou dispositivo externo.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="8726c-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="8726c-117">**Permitir que um usuário agende eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="8726c-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="8726c-118">Se o usuário tiver atribuído a política global, execute e verifique se *o parâmetro AllowBroadcastScheduling* está definido como *True*:</span><span class="sxs-lookup"><span data-stu-id="8726c-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="8726c-119">Em seguida, atribua o usuário à política global, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="8726c-120">Cenários de usuário</span><span class="sxs-lookup"><span data-stu-id="8726c-120">User scenarios</span></span>
<span data-ttu-id="8726c-121">**Você deseja que todos os usuários em sua organização sejam capazes de agendar eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="8726c-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="8726c-122">Se os usuários são atribuídos à política global, execute e verifique se *AllowBroadcastScheduling* \*está definido como *True*:</span><span class="sxs-lookup"><span data-stu-id="8726c-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="8726c-123">Se os usuários são atribuídos a uma política diferente da política global, execute e verifique se *-AllowBroadcastScheduling* está definido como *True*:</span><span class="sxs-lookup"><span data-stu-id="8726c-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="8726c-124">**Você deseja que o agendamento de eventos ao vivo seja desabilitado em toda a sua organização**</span><span class="sxs-lookup"><span data-stu-id="8726c-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="8726c-125">Desabilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="8726c-126">Atribua todos os usuários da sua organização à política global, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="8726c-127">**Você deseja que um grande número de usuários possa agendar eventos ao vivo e impedir que um conjunto de usuários agende-os**</span><span class="sxs-lookup"><span data-stu-id="8726c-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="8726c-128">Execute e verifique se *AllowBroadcastScheduling* está definido como *True*:</span><span class="sxs-lookup"><span data-stu-id="8726c-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="8726c-129">Em seguida, atribua um usuário ou usuários à política global, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="8726c-130">Crie uma nova política que não permita o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="8726c-131">Desabilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="8726c-132">Em seguida, atribua usuários a essa política, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="8726c-133">**Você deseja desabilitar o agendamento de eventos ao vivo para um grande número de usuários e permitir que um conjunto de usuários agende-os**</span><span class="sxs-lookup"><span data-stu-id="8726c-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="8726c-134">Desabilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="8726c-135">Em seguida, atribua esses usuários à política global, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="8726c-136">Crie uma política para permitir o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="8726c-137">Habilitar o agendamento de eventos ao vivo, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="8726c-138">Em seguida, atribua usuários a essa política, execute:</span><span class="sxs-lookup"><span data-stu-id="8726c-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="8726c-139">Definir quem pode participar de eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="8726c-139">Set who can join live events</span></span>
 
<span data-ttu-id="8726c-140">De definir a política global para permitir que os usuários criem eventos que todos, incluindo usuários anônimos, possam participar, executem:</span><span class="sxs-lookup"><span data-stu-id="8726c-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="8726c-141">Definir a opção de gravação para eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="8726c-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="8726c-142">Essa configuração se aplica apenas a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="8726c-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="8726c-143">De definir a política global para desabilitar a gravação para eventos ao vivo:</span><span class="sxs-lookup"><span data-stu-id="8726c-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="8726c-144">Definir legendas e legendas ao vivo em eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="8726c-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="8726c-145">Essa configuração se aplica apenas a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="8726c-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="8726c-146">Definir a política global para ativar legendas e legendas ao vivo (transcrição) para participantes do evento:</span><span class="sxs-lookup"><span data-stu-id="8726c-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="8726c-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8726c-147">Related topics</span></span>
- [<span data-ttu-id="8726c-148">Configurar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="8726c-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="8726c-149">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="8726c-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)