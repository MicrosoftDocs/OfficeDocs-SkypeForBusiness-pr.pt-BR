---
title: Usar o PowerShell para definir políticas de eventos ao vivo
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Exemplos de como usar o PowerShell para definir políticas no Teams para controlar quem pode realizar eventos ao vivo em sua organização e os recursos disponíveis nos eventos.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ef243860ea1450dcd5539d3d5b01025e7eac55cd
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767571"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usar o PowerShell para definir políticas de eventos ao vivo no Microsoft Teams

Você pode usar os seguintes cmdlets Windows PowerShell para definir e atribuir configurações de política para eventos ao vivo no Teams:

- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)

Aqui estão alguns exemplos.

> [!NOTE]
> Antes de executar esses cmdlets, você deve estar conectado ao Skype for Business PowerShell Online. Para obter mais informações, consulte [Gerenciar Skype for Business Online com o Microsoft 365 ou Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Permitir que os usuários agendem eventos ao vivo

> [!NOTE]
> Esses exemplos são para eventos produzidos no Teams.

### <a name="allow-a-user-to-schedule-live-events"></a>Permitir que um usuário agende eventos ao vivo

Se o usuário receber a política global, execute e verifique se o parâmetro *AllowBroadcastScheduling* será definido como *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

Em seguida, atribua o usuário à política global, execute:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Cenários de usuário

#### <a name="you-want-all-users-in-your-organization-to-be-able-to-schedule-live-events"></a>Você deseja que todos os usuários da sua organização possam agendar eventos ao vivo

Se os usuários receberem a política global, execute e verifique se *AllowBroadcastScheduling* está definido como *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

Se os usuários receberem uma política diferente da política global, execute e verifique se *-AllowBroadcastScheduling* será definido como *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

#### <a name="you-want-live-events-scheduling-to-be-disabled-across-your-organization"></a>Você deseja que o agendamento de eventos ao vivo seja desabilitado em toda a sua organização

Desabilitar o agendamento de eventos ao vivo, execute:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

Atribua todos os usuários da sua organização à política global, execute:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="you-want-a-large-number-of-users-to-be-able-to-schedule-live-events-and-prevent-a-set-of-users-from-scheduling-them"></a>Você deseja que um grande número de usuários possa agendar eventos ao vivo e impedir que um conjunto de usuários os agende

Execute e verifique se *AllowBroadcastScheduling* está definido como *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```

Em seguida, atribua um usuário ou usuário à política global, execute:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Crie uma nova política que não permita agendar eventos ao vivo, execute:

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```

Desabilitar o agendamento de eventos ao vivo, execute:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```

Em seguida, atribua usuários a essa política, execute:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```

#### <a name="you-want-to-disable-live-event-scheduling-for-a-large-number-of-the-users-and-allow-a-set-of-users-to-schedule-them"></a>Você deseja desabilitar o agendamento de eventos ao vivo para um grande número de usuários e permitir que um conjunto de usuários os agende

Desabilitar o agendamento de eventos ao vivo, execute:

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

## <a name="set-who-can-join-live-events"></a>Definir quem pode participar de eventos ao vivo

Defina a política global para permitir que os usuários criem eventos que todos, incluindo usuários anônimos, podem participar, executar:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```

## <a name="set-the-recording-option-for-live-events"></a>Definir a opção de gravação para eventos ao vivo

> [!NOTE]
> Essa configuração se aplica apenas a eventos produzidos no Teams.

Defina a política global para desabilitar a gravação para eventos ao vivo:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```

## <a name="set-live-captions-and-subtitles-in-live-events"></a>Definir legendas e legendas ao vivo em eventos ao vivo

> [!NOTE]
> Essa configuração se aplica apenas a eventos produzidos no Teams.

Defina a política global para ativar legendas e legendas ao vivo (transcrição) para os participantes do evento:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Tópicos relacionados

- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
- [Visão Geral do PowerShell do Teams](../teams-powershell-overview.md)
