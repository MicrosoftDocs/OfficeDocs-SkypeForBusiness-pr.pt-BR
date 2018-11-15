---
title: Use o PowerShell para definir políticas de eventos ao vivo em Teams da Microsoft
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Exemplos de como usar o PowerShell para definir políticas em equipes para controlar quem pode conter eventos ao vivo na sua organização e os recursos que estão disponíveis nos eventos que eles criam
appliesto:
- Microsoft Teams
ms.openlocfilehash: f802c2b67c0a4cd4b0838dd9aeec9c4bbf884968
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26535870"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Use o PowerShell para definir políticas de eventos ao vivo em Teams da Microsoft
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Você pode usar os seguintes cmdlets do Windows PowerShell para definir e atribuir configurações de diretiva para eventos ao vivo em equipes: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Eis alguns exemplos.

## <a name="allow-users-to-schedule-live-events"></a>Permitir que os usuários agendem eventos ao vivo 

> [!NOTE]
> Esses exemplos são para eventos de início rápido. Para eventos externos codificador, há etapas adicionais que você deve fazer. Para obter mais informações, consulte [habilitar usuários agendar a eventos externos codificador](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).

**Permitir que um usuário agendar eventos ao vivo**

Se o usuário é atribuído a política global, execute e verificar se o parâmetro *AllowBroadcastScheduling* está definido como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Atribua o usuário para a política global, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Cenários de usuário
**Você deseja que todos os usuários em sua organização possam agendar eventos ao vivo**

Se os usuários são atribuídos a política global, execute e confirme que *AllowBroadcastScheduling* * estiver definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se os usuários são atribuídos a uma política que não seja a política global, execute e verificar se a opção *-AllowBroadcastScheduling* está definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Você deseja agendar a ser desabilitado em toda a organização de eventos ao vivo**

Desabilitar o agendamento de eventos ao vivo, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Atribua a todos os usuários em sua organização para a política global, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Você deseja um grande número de usuários possam agendar eventos ao vivo e impedir que um conjunto de usuários agendamento-los**

Execute e verificar se *AllowBroadcastScheduling* está definida como *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Em seguida, atribua um ou mais usuários para a política global, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Crie uma nova política que não permite agendar eventos ao vivo, executados:
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy
```
Desabilitar o agendamento de eventos ao vivo, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Atribua usuários a essa diretiva, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Você deseja desabilitar o agendamento para um grande número de usuários de evento ao vivo e permitir que um conjunto de usuários para agendá-las**

Desabilitar o agendamento de eventos ao vivo, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Em seguida, atribua esses usuários para a política global, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crie uma diretiva para permitir o agendamento de eventos ao vivo, execute:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilitar o agendamento de eventos ao vivo, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Atribua usuários a essa diretiva, execute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Definir quem pode ingressar eventos ao vivo
 
Defina a política global que permite aos usuários criar eventos que todos, inclusive usuários anônimos, que pode participar, execute:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Definir a opção de gravação para eventos ao vivo
> [!NOTE]
> Essa configuração se aplica apenas a eventos de início rápido.

Defina a política global para desabilitar o registro de eventos ao vivo:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>Definir a transcrição e uma tradução em eventos ao vivo (em breve)
> [!NOTE]
> Essa configuração se aplica apenas a eventos de início rápido. 

Defina a política global para ativar na transcrição e uma tradução para os participantes do evento:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Tópicos relacionados
- [Configurar para equipes eventos ao vivo](set-up-for-teams-live-events.md)


