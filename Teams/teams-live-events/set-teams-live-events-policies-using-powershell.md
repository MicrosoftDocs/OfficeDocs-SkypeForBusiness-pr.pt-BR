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
ms.openlocfilehash: 4d5f1cceb42afd2be92aedcd0a40af4e23650512
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140642"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="d4f51-103">Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4f51-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="d4f51-104">Você pode usar os seguintes cmdlets do Windows PowerShell para definir e atribuir configurações de política para eventos dinâmicos no Teams:</span><span class="sxs-lookup"><span data-stu-id="d4f51-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="d4f51-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f51-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="d4f51-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f51-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="d4f51-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f51-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="d4f51-108">Grant CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f51-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="d4f51-109">Aqui estão alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="d4f51-109">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="d4f51-110">Antes de poder executar esses cmdlets, você deve estar conectado ao Skype for Business online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4f51-110">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="d4f51-111">Para obter mais informações, consulte [gerenciar o Skype for Business online com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4f51-111">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="d4f51-112">Permitir que os usuários agendem eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="d4f51-112">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="d4f51-113">Esses exemplos são para eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f51-113">These examples are for events produced in Teams.</span></span> <span data-ttu-id="d4f51-114">Para eventos produzidos com um aplicativo ou dispositivo externo, há etapas adicionais que você deve fazer.</span><span class="sxs-lookup"><span data-stu-id="d4f51-114">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="d4f51-115">Para obter mais informações, consulte [habilitar usuários para agendar eventos que foram produzidos com um aplicativo ou dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="d4f51-115">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="d4f51-116">**Permitir que um usuário agende eventos ao vivo**</span><span class="sxs-lookup"><span data-stu-id="d4f51-116">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="d4f51-117">Se o usuário tiver atribuído a política global, execute e verifique se o parâmetro *AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="d4f51-117">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="d4f51-118">Em seguida, atribua o usuário à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-118">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="d4f51-119">Cenários de usuário</span><span class="sxs-lookup"><span data-stu-id="d4f51-119">User scenarios</span></span>
<span data-ttu-id="d4f51-120">**Você quer que todos os usuários da sua organização possam agendar eventos dinâmicos**</span><span class="sxs-lookup"><span data-stu-id="d4f51-120">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="d4f51-121">Se os usuários tiverem atribuído a política global, execute e verifique se *AllowBroadcastScheduling* \* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="d4f51-121">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="d4f51-122">Se os usuários receberem uma política diferente da política global, execute e verifique se *-AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="d4f51-122">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="d4f51-123">**Você deseja que o agendamento de eventos dinâmicos seja desabilitado em toda a sua organização**</span><span class="sxs-lookup"><span data-stu-id="d4f51-123">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="d4f51-124">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-124">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="d4f51-125">Atribuir todos os usuários de sua organização à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-125">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="d4f51-126">**Você quer que um grande número de usuários possa agendar eventos dinâmicos e impedir que um conjunto de usuários o agende**</span><span class="sxs-lookup"><span data-stu-id="d4f51-126">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="d4f51-127">Execute e verifique se o *AllowBroadcastScheduling* está definido como *true*:</span><span class="sxs-lookup"><span data-stu-id="d4f51-127">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="d4f51-128">Em seguida, atribua um usuário ou usuários à política global, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-128">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="d4f51-129">Criar uma nova política que não permita eventos dinâmicos de agendamento, execute:</span><span class="sxs-lookup"><span data-stu-id="d4f51-129">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="d4f51-130">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-130">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="d4f51-131">Em seguida, atribua usuários a essa política, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-131">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="d4f51-132">**Você deseja desabilitar o agendamento de eventos dinâmicos para um grande número de usuários e permitir que um conjunto de usuários os agende**</span><span class="sxs-lookup"><span data-stu-id="d4f51-132">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="d4f51-133">Desabilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-133">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="d4f51-134">Em seguida, atribua a esses usuários a política global, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-134">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="d4f51-135">Criar uma política para permitir agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-135">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="d4f51-136">Habilitar agendamento de eventos dinâmicos, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-136">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="d4f51-137">Em seguida, atribua usuários a essa política, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-137">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="d4f51-138">Definir quem pode participar de eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="d4f51-138">Set who can join live events</span></span>
 
<span data-ttu-id="d4f51-139">Defina a política global para permitir que os usuários criem eventos que todos, incluindo usuários anônimos, possam participar, executar:</span><span class="sxs-lookup"><span data-stu-id="d4f51-139">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="d4f51-140">Definir a opção de gravação para eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="d4f51-140">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="d4f51-141">Essa configuração se aplica somente a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f51-141">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="d4f51-142">Defina a política global para desabilitar a gravação de eventos dinâmicos:</span><span class="sxs-lookup"><span data-stu-id="d4f51-142">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="d4f51-143">Definir legendas ao vivo e legendas em eventos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="d4f51-143">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="d4f51-144">Essa configuração se aplica somente a eventos produzidos no Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f51-144">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="d4f51-145">Defina a política global para ativar legendas dinâmicas e legendas (transcrição) para participantes do evento:</span><span class="sxs-lookup"><span data-stu-id="d4f51-145">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="d4f51-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d4f51-146">Related topics</span></span>
- [<span data-ttu-id="d4f51-147">Configurar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="d4f51-147">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="d4f51-148">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="d4f51-148">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

