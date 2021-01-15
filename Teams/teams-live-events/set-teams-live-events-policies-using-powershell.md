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
description: Exemplos de como usar o PowerShell para definir políticas no Teams para controlar quem pode manter eventos ao vivo em sua organização e os recursos disponíveis nos eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815621"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams

Você pode usar os seguintes Windows PowerShell cmdlets para definir e atribuir configurações de política para eventos ao vivo no Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Aqui estão alguns exemplos.

> [!NOTE]
> Antes de poder executar esses cmdlets, você deve estar conectado ao PowerShell do Skype for Business Online. Para obter mais informações, [consulte Gerenciar o Skype for Business Online com o Microsoft 365 ou o Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="allow-users-to-schedule-live-events"></a>Permitir que os usuários agendem eventos ao vivo 

> [!NOTE]
> Esses exemplos são para eventos produzidos no Teams. Para eventos produzidos com um aplicativo ou dispositivo externo, há etapas adicionais que você deve fazer. Para obter mais informações, consulte [Permitir que os usuários agendem eventos que foram produzidos com um aplicativo ou dispositivo externo.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**Permitir que um usuário agende eventos ao vivo**

Se o usuário tiver a política global atribuída, execute e verifique se o parâmetro *AllowBroadcastScheduling* está definido como *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Em seguida, atribua o usuário à política global, execute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Cenários do usuário
**Você deseja que todos os usuários em sua organização sejam capazes de agendar eventos ao vivo**

Se os usuários são atribuídos à política global, execute e verifique se *AllowBroadcastScheduling* *está definido como *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se os usuários são atribuídos a uma política diferente da política global, execute e verifique se *-AllowBroadcastScheduling* está definido como *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Você deseja que o agendamento de eventos ao vivo seja desabilitado em toda a organização**

Desabilite o agendamento de eventos ao vivo, execute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Atribua todos os usuários de sua organização à política global, execute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Você deseja que um grande número de usuários seja capaz de agendar eventos ao vivo e impedir que um conjunto de usuários os agende**

Execute e verifique se *AllowBroadcastScheduling* está definido como *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Em seguida, atribua um usuário ou usuários à política global, execute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Crie uma nova política que não permita o agendamento de eventos ao vivo, execute:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Desabilite o agendamento de eventos ao vivo, execute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Em seguida, atribua usuários a essa política, execute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Você deseja desabilitar o agendamento de eventos ao vivo para um grande número de usuários e permitir que um conjunto de usuários os agende**

Desabilite o agendamento de eventos ao vivo, execute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Em seguida, atribua esses usuários à política global, execute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crie uma política para permitir o agendamento de eventos ao vivo, execute:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilitar o agendamento de eventos ao vivo, execute:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Em seguida, atribua usuários a essa política, execute:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Definir quem pode ingressar em eventos ao vivo
 
Definir a política global para permitir que os usuários criem eventos que todos, incluindo usuários anônimos, possam participar, executem:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Definir a opção de gravação para eventos ao vivo
> [!NOTE]
> Essa configuração se aplica somente a eventos produzidos no Teams.

De configurar a política global para desabilitar a gravação de eventos ao vivo:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Definir legendas e legendas ao vivo em eventos ao vivo
> [!NOTE]
> Essa configuração se aplica somente a eventos produzidos no Teams. 

Definir a política global para ativar legendas ao vivo e legendas (transcrição) para participantes do evento:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Tópicos relacionados
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Visão Geral do PowerShell do Teams](../teams-powershell-overview.md)

