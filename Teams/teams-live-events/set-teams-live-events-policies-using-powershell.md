---
title: Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
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
ms.openlocfilehash: 825fe7e7e80b2653d35c8b0752124b50386395d6
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35602259"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams

Você pode usar os seguintes cmdlets do Windows PowerShell para definir e atribuir configurações de política para eventos dinâmicos no Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Aqui estão alguns exemplos.

## <a name="allow-users-to-schedule-live-events"></a>Permitir que os usuários agendem eventos dinâmicos 

> [!NOTE]
> Esses exemplos são para eventos produzidos no Teams. Para eventos produzidos com um aplicativo ou dispositivo externo, há etapas adicionais que você deve fazer. Para obter mais informações, consulte [habilitar usuários para agendar eventos que foram produzidos com um aplicativo ou dispositivo externo](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Permitir que um usuário agende eventos ao vivo**

Se o usuário tiver atribuído a política global, execute e verifique se o parâmetro *AllowBroadcastScheduling* está definido como *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Em seguida, atribua o usuário à política global, executar:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Cenários de usuário
**Você quer que todos os usuários da sua organização possam agendar eventos dinâmicos**

Se os usuários tiverem atribuído a política global, execute e verifique se *AllowBroadcastScheduling* * está definido como *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se os usuários receberem uma política diferente da política global, execute e verifique se *-AllowBroadcastScheduling* está definido como *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Você deseja que o agendamento de eventos dinâmicos seja desabilitado em toda a sua organização**

Desabilitar agendamento de eventos dinâmicos, executar:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Atribuir todos os usuários de sua organização à política global, executar:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Você quer que um grande número de usuários possa agendar eventos dinâmicos e impedir que um conjunto de usuários o agende**

Execute e verifique se o *AllowBroadcastScheduling* está definido como *true*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Em seguida, atribua um usuário ou usuários à política global, executar:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Criar uma nova política que não permita eventos dinâmicos de agendamento, execute:
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Desabilitar agendamento de eventos dinâmicos, executar:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Em seguida, atribua usuários a essa política, executar:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Você deseja desabilitar o agendamento de eventos dinâmicos para um grande número de usuários e permitir que um conjunto de usuários os agende**

Desabilitar agendamento de eventos dinâmicos, executar:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Em seguida, atribua a esses usuários a política global, executar:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Criar uma política para permitir agendamento de eventos dinâmicos, executar:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilitar agendamento de eventos dinâmicos, executar:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Em seguida, atribua usuários a essa política, executar:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Definir quem pode participar de eventos dinâmicos
 
Defina a política global para permitir que os usuários criem eventos que todos, incluindo usuários anônimos, possam participar, executar:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Definir a opção de gravação para eventos dinâmicos
> [!NOTE]
> Essa configuração se aplica somente a eventos produzidos no Teams.

Defina a política global para desabilitar a gravação de eventos dinâmicos:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Definir legendas ao vivo e legendas em eventos dinâmicos
> [!NOTE]
> Essa configuração se aplica somente a eventos produzidos no Teams. 

Defina a política global para ativar legendas dinâmicas e legendas (transcrição) para participantes do evento:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Tópicos relacionados
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)


