---
title: Gerenciar o acesso baseado em turnos para trabalhadores da linha de frente Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar o acesso baseado em turnos Teams trabalhadores de linha de frente em sua organização.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675213"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gerenciar o acesso baseado em turnos para trabalhadores da linha de frente Teams
## <a name="overview"></a>Visão Geral

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A presença Microsoft Teams indica a disponibilidade e o status atuais de um usuário para outros usuários. A presença de trabalhadores da linha de frente geralmente é menos previsível do que outras equipes, pois suas horas de trabalho normalmente não são as mesmas a cada dia. Como administrador, você pode configurar o Teams para mostrar um conjunto de estados de presença baseados em turnos para os trabalhadores da linha de frente em sua organização indicarem quando eles estão no turno de entrada e de folga.

Esses estados de presença baseados em turnos&mdash;![Marca de seleção verde sólida, indica No turno.](../../media/flw-presence-on-shift.png) **No turno**, ![círculo cinza com x, indica Off shift.](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy are separate**&mdash;from the [default set of presence states](../../presence-admins.md) in Teams. Com esses dois conjuntos de estados de presença, você pode configurar experiências diferentes para as pessoas em sua organização com base em sua função.

Com o acesso baseado em turnos, você pode gerenciar o acesso Teams quando os trabalhadores da linha de frente estão fora do turno. Por exemplo, você pode definir Teams para exibir uma mensagem que os trabalhadores da linha de frente devem reconhecer antes de usar Teams quando não estiverem em um turno agendado.  

## <a name="scenario"></a>Cenário

Aqui está um exemplo de como sua organização pode gerenciar o acesso baseado em turnos.

Você tem trabalhadores de linha de frente em sua organização que só devem ser pagos por horas que trabalham em um turno agendado e aprovado pelo gerente. Eles não devem ser pagos pelo tempo gasto trabalhando fora de um turno agendado, o que inclui o uso do Teams aplicativo. Você configura uma mensagem personalizada que diz "Seu tempo no turno Teams quando estiver fora do turno não contará para horas faturáveis", que é exibida quando os trabalhadores da linha de frente tentam acessar Teams quando estão fora do turno. Se eles optarem por usar Teams, clicarão em Aceitar  com a compreensão de que não serão pagos por esse tempo.

Você também tem funcionários de informações em sua organização que são assalariados e que não trabalham em turnos. Você configura seus operadores de informações para usar os estados de presença padrão Teams ao mesmo tempo que fornece aos seus trabalhadores de linha de frente a presença baseada em turnos.

## <a name="shift-based-presence-states"></a>Estados de presença baseados em shift

Aqui estão os estados de presença baseados em turnos.

|Aplicativo configurado |Usuário configurado  |Mais informações  |
|---------|---------|---------|
|![Marca de seleção verde sólida, indica No turno.](../../media/flw-presence-on-shift.png) No turno     |         |Definido automaticamente no início de um turno         |
|![Círculo cinza com x, indica Deslocamento desativado](../../media/flw-presence-off-shift.png) Fora do turno     |         |Definido automaticamente no final de um turno         |
|![Círculo vermelho sólido, indica Ocupado.](../../media/flw-presence-busy.png) Ocupado      | ![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Definido automaticamente. Também pode ser definido manualmente quando o trabalho de linha de frente está no turno.|

## <a name="off-shift-access-to-teams"></a>Desative o acesso ao Teams

Esse recurso permite que você gerencie o acesso Teams quando os trabalhadores da linha de frente estão fora do turno. Você pode definir Teams para exibir uma mensagem para os trabalhadores da linha de frente se eles acessarem Teams quando estiverem fora do turno. Os trabalhadores da linha de frente **devem clicar em Aceitar** para confirmar a mensagem antes que possam usar Teams.

Você pode usar a mensagem padrão, escolher entre um conjunto de mensagens predefinido ou personalizar a mensagem para exibir qualquer texto desejado. Esta é a mensagem padrão:

![Captura de tela da mensagem padrão.](../../media/shifts-presence-message.png)

Você também pode definir a frequência quando a mensagem é exibida e definir um período de carência entre quando o primeiro turno é iniciado ou o último turno termina e quando o acesso Teams é restrito.

## <a name="manage-shift-based-access"></a>Gerenciar o acesso baseado em turnos

Como administrador, você usa políticas para controlar a presença baseada em turnos para trabalhadores de linha de frente em sua organização. Você gerencia essas políticas usando os seguintes cmdlets do PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Use o cmdlet New-CsTeamsShiftsPolicy para criar uma nova política, defina as configurações de política desejadas e, em seguida, use o cmdlet Grant-CsTeamsShiftsPolicy para atribuir a política aos usuários.

Aqui estão alguns exemplos. Para obter informações detalhadas sobre cada configuração de política e parâmetro, incluindo a lista de mensagens de deslocamento desativadas predefinidos que você pode escolher, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Exemplo 1

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Default Message. Nesta política, a presença baseada em turnos é ativada e a mensagem padrão é exibida sempre que um usuário que recebe essa política acessa Teams quando está fora do turno. O usuário poderá usar Teams quando estiver fora do turno se aceitar a mensagem, e o período de carência entre quando o primeiro turno inicia ou o último turno termina e quando o acesso é restrito é de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Exemplo 2 

Neste exemplo, criamos uma nova política chamada Off Shift Teams Acessar Mensagem Personalizada. Nesta política, a presença baseada em turnos é ativada e uma mensagem personalizada é exibida sempre que um usuário atribuído a essa política Teams quando está fora do turno. O usuário poderá usar Teams quando estiver fora do turno se aceitar a mensagem, e o período de carência entre quando o primeiro turno é iniciado ou o último turno termina e quando o acesso é restrito é de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para saber mais, confira [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Exemplo 3

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Message1. Nessa política, a presença baseada em turnos é ativada e a seguinte mensagem predefinida é exibida sempre que um usuário que recebe essa política acessa Teams quando está fora do turno.

  "Seu empregador não autoriza nem aprova o uso de sua rede, aplicativos, sistemas ou ferramentas por funcionários não isentos ou por hora durante seu horário de trabalho. Ao aceitar, você reconhece que o uso de Teams fora do turno não está autorizado e não será compensado." 

O usuário poderá usar Teams quando estiver fora do turno se aceitar a mensagem, e o período de carência entre quando o primeiro turno inicia ou o último turno termina e quando o acesso é restrito é de três minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Exemplo 4

Neste exemplo, atribuímos uma política chamada Off Shift Teams Acessar Mensagem Personalizada a um usuário chamado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o aplicativo Shifts para sua organização no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)