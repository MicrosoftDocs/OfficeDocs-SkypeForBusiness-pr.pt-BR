---
title: Usar o PowerShell para definir políticas de eventos dinâmicos
author: lanachin
ms.author: v-lanac
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
description: Exemplos de como usar o PowerShell para definir diretivas em equipes para controlar quem pode manter eventos dinâmicos em sua organização e os recursos disponíveis nos eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d83dd66914c835f62028fc4941da34646c75411d
ms.sourcegitcommit: c49698e03fa3bdd7c82496189b200ac6bb4e05a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48320796"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="52e3b-103">Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52e3b-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="52e3b-104">Você pode usar os seguintes cmdlets do Windows PowerShell para definir e atribuir configurações de política para eventos dinâmicos no Teams:</span><span class="sxs-lookup"><span data-stu-id="52e3b-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="52e3b-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52e3b-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52e3b-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52e3b-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52e3b-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52e3b-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52e3b-108">Grant CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52e3b-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52e3b-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="52e3b-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="52e3b-110">Aqui estão alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="52e3b-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="52e3b-111">Antes de poder executar esses cmdlets, você deve estar conectado ao Skype for Business online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52e3b-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="52e3b-112">Para obter mais informações, consulte [gerenciar o Skype for Business online com o Microsoft 365 ou o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="52e3b-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="52e3b-113">Permitir que os usuários agendem eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="52e3b-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="52e3b-114">Esses exemplos são para eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="52e3b-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="52e3b-115">Para eventos produzidos com um aplicativo ou dispositivo externo, há etapas adicionais que você deve fazer.</span><span class="sxs-lookup"><span data-stu-id="52e3b-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="52e3b-116">Para obter mais informações, consulte [habilitar usuários para agendar eventos que foram produzidos com um aplicativo ou dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="52e3b-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="52e3b-117">**Permitir que um usuário agende eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="52e3b-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="52e3b-118">Se o usuário tiver atribuído a política global, execute e verifique se o parâmetro *AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="52e3b-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="52e3b-119">Em seguida, atribua o usuário à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="52e3b-120">Cenários de usuário</span><span class="sxs-lookup"><span data-stu-id="52e3b-120">User scenarios</span></span>
<span data-ttu-id="52e3b-121">**Você quer que todos os usuários da sua organização possam agendar eventos dinâmicos**</span><span class="sxs-lookup"><span data-stu-id="52e3b-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="52e3b-122">Se os usuários tiverem atribuído a política global, execute e verifique se *AllowBroadcastScheduling* \* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="52e3b-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="52e3b-123">Se os usuários receberem uma política diferente da política global, execute e verifique se *-AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="52e3b-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="52e3b-124">**Você deseja que o agendamento de eventos dinâmicos seja desabilitado em toda a sua organização**</span><span class="sxs-lookup"><span data-stu-id="52e3b-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="52e3b-125">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="52e3b-126">Atribuir todos os usuários de sua organização à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="52e3b-127">**Você quer que um grande número de usuários possa agendar eventos dinâmicos e impedir que um conjunto de usuários o agende**</span><span class="sxs-lookup"><span data-stu-id="52e3b-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="52e3b-128">Execute e verifique se o *AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="52e3b-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="52e3b-129">Em seguida, atribua um usuário ou usuários à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="52e3b-130">Criar uma nova política que não permita eventos dinâmicos de agendamento, execute:</span><span class="sxs-lookup"><span data-stu-id="52e3b-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="52e3b-131">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="52e3b-132">Em seguida, atribua usuários a essa política, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="52e3b-133">**Você deseja desabilitar o agendamento de eventos dinâmicos para um grande número de usuários e permitir que um conjunto de usuários os agende**</span><span class="sxs-lookup"><span data-stu-id="52e3b-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="52e3b-134">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="52e3b-135">Em seguida, atribua a esses usuários a política global, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="52e3b-136">Criar uma política para permitir agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="52e3b-137">Habilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="52e3b-138">Em seguida, atribua usuários a essa política, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="52e3b-139">Definir quem pode participar de eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="52e3b-139">Set who can join live events</span></span>
 
<span data-ttu-id="52e3b-140">Defina a política global para permitir que os usuários criem eventos que todos, incluindo usuários anônimos, possam participar, executar:</span><span class="sxs-lookup"><span data-stu-id="52e3b-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="52e3b-141">Definir a opção de gravação para eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="52e3b-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="52e3b-142">Essa configuração se aplica somente a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="52e3b-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="52e3b-143">Defina a política global para desabilitar a gravação de eventos dinâmicos:</span><span class="sxs-lookup"><span data-stu-id="52e3b-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="52e3b-144">Definir legendas ao vivo e legendas em eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="52e3b-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="52e3b-145">Essa configuração se aplica somente a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="52e3b-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="52e3b-146">Defina a política global para ativar legendas dinâmicas e legendas (transcrição) para participantes do evento:</span><span class="sxs-lookup"><span data-stu-id="52e3b-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="52e3b-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="52e3b-147">Related topics</span></span>
- [<span data-ttu-id="52e3b-148">Configurar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="52e3b-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="52e3b-149">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="52e3b-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

