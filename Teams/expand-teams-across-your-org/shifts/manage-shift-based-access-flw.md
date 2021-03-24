---
title: Gerenciar o acesso baseado em turnos para funcionários de linha de frente no Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar o acesso baseado em turnos no Teams for Frontline Workers em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092539"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gerenciar o acesso baseado em turnos para funcionários de linha de frente no Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi desativado. Estamos criando recursos do StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo Shifts para o gerenciamento de cronogramas e recursos adicionais serão implantados com o tempo. O StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Todas as pessoas que tentarem abrir o StaffHub receberão uma mensagem direcionando-as para o download do Teams. Para saber mais, confira [O Microsoft StaffHub foi desativado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Visão Geral

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A presença no Microsoft Teams indica a disponibilidade atual e o status de um usuário para outros usuários. A presença de Trabalhadores de Linha de Frente geralmente é menos previsível do que outras equipes, pois suas horas de trabalho normalmente não são as mesmas a cada dia. Como administrador, você pode configurar o Teams para mostrar um conjunto de estados de presença baseados em turnos para os Funcionários de Linha de Frente em sua organização indicarem quando eles estão no turno de entrada e de folga.

Esses estados de presença baseados em turnos Marca de verificação verde sólido, indica On shift On shift , Gray &mdash; ![ circle with ](../../media/flw-presence-on-shift.png) x, indicates Off shift Off , Solid ![ red ](../../media/flw-presence-off-shift.png)  ![ circle, indicates Busy ](../../media/flw-presence-busy.png) **Busy** &mdash; [](../../presence-admins.md) are separate from the default set of presence states in Teams. Com esses dois conjuntos de estados de presença, você pode configurar experiências diferentes para pessoas em sua organização com base em suas funções.

Com o acesso baseado em turnos, você pode gerenciar o acesso ao Teams quando os Trabalhadores de Linha de Frente estão fora do turno. Por exemplo, você pode definir o Teams para exibir uma mensagem que os Funcionários de Linha de Frente devem reconhecer antes de usar o Teams quando não estão em um turno agendado.  

## <a name="scenario"></a>Cenário

Veja um exemplo de como sua organização pode gerenciar o acesso baseado em turnos.

Você tem Trabalhadores de Linha de Frente em sua organização que devem ser pagos apenas por horas em que trabalham em um turno agendado e aprovado pelo gerente. Eles não devem ser pagos pelo tempo gasto trabalhando fora de um turno agendado, o que inclui o uso do aplicativo Teams. Você configura uma mensagem personalizada que diz "Seu tempo no Teams quando estiver fora do turno não contará em direção ao horário de pagamento", que é exibido quando os Trabalhadores de Linha de Frente tentam acessar o Teams quando estão fora do turno. Se eles optarem por usar o Teams, eles clicam em **Eu aceito** com o entendimento de que eles não serão pagos por esse tempo.

Você também tem funcionários de informações em sua organização que são assalariados e que não trabalham em turnos. Você configura seus funcionários de informações para usar os estados de presença padrão no Teams ao mesmo tempo que dá sua presença baseada em turnos dos Trabalhadores de Linha de Frente.

## <a name="shift-based-presence-states"></a>Estados de presença baseados em turnos

Aqui estão os estados de presença baseados em turnos.

|Aplicativo configurado |Usuário configurado  |Mais informações  |
|---------|---------|---------|
|![Marca de verificação verde sólido, indica No turno](../../media/flw-presence-on-shift.png) No turno     |         |Definir automaticamente no início de um turno         |
|![Círculo cinza com x, indica Off shift](../../media/flw-presence-off-shift.png) Off shift     |         |Definir automaticamente no final de um turno         |
|![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Definir automaticamente. Também pode ser definido manualmente quando o Trabalho de Linha de Frente está no turno.|

## <a name="off-shift-access-to-teams"></a>Off shift access to Teams

Esse recurso permite que você gerencie o acesso ao Teams quando os Trabalhadores de Linha de Frente estão fora do turno. Você pode definir o Teams para exibir uma mensagem aos Trabalhadores de Linha de Frente se eles acessarem o Teams quando estão fora do turno. Os Funcionários de Linha de Frente **devem clicar em Aceito** para reconhecer a mensagem antes que eles possam usar o Teams.

Você pode usar a mensagem padrão, escolher de um conjunto de mensagens pré-definidas ou personalizar a mensagem para exibir qualquer texto que você deseja. Aqui está a mensagem padrão:

![Captura de tela da mensagem padrão](../../media/shifts-presence-message.png)

Você também pode definir a frequência quando a mensagem é exibida e definir um período de carência entre quando o primeiro turno é iniciado ou o último turno termina e quando o acesso ao Teams é restrito.

## <a name="manage-shift-based-access"></a>Gerenciar o acesso baseado em turnos

Como administrador, você usa políticas para controlar a presença baseada em turnos para Trabalhadores de Linha de Frente em sua organização. Você gerencia essas políticas usando os seguintes cmdlets do PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Use o cmdlet New-CsTeamsShiftsPolicy para criar uma nova política, de definir as configurações de política que você deseja e, em seguida, use o cmdlet Grant-CsTeamsShiftsPolicy para atribuir a política aos usuários.

Aqui estão alguns exemplos. Para obter informações detalhadas sobre cada configuração de política e parâmetro, incluindo a lista de mensagens de turno off predefinidos que você pode escolher, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Exemplo 1

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Default Message. Nesta política, a presença baseada em turnos é íntequeada e a mensagem padrão é exibida sempre que um usuário atribuído a essa política acessa o Teams quando está fora do turno. O usuário pode usar o Teams quando estiver fora do turno se aceitar a mensagem, e o período de carência entre quando o primeiro turno é iniciado ou o último turno termina e quando o acesso é restrito é de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para este parâmetro, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Exemplo 2 

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Custom Message. Nesta política, a presença baseada em turnos é 24h e uma mensagem personalizada é exibida sempre que um usuário atribuído a essa política acessa o Teams quando está fora do turno. O usuário pode usar o Teams quando estiver fora do turno se aceitar a mensagem, e o período de carência entre quando o primeiro turno é iniciado ou o último turno termina e quando o acesso é restrito é de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para saber mais, confira [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Exemplo 3

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Message1. Nesta política, a presença baseada em turnos é ativa e a seguinte mensagem predefinida é exibida sempre que um usuário atribuído a essa política acessa o Teams quando está fora do turno.

  "Seu empregador não autoriza ou aprova o uso de sua rede, aplicativos, sistemas ou ferramentas por funcionários não isentos ou por hora durante seu horário não comercial. Ao aceitar, você reconhece que o uso do Teams enquanto estiver fora do turno não está autorizado e não será compensado." 

O usuário pode usar o Teams quando estiver fora do turno se aceitar a mensagem, e o período de carência entre quando o primeiro turno é iniciado ou o último turno termina e quando o acesso é restrito é de três minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para este parâmetro, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Exemplo 4

Neste exemplo, atribuímos uma política chamada Off Shift Teams Access Custom Message a um usuário chamado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o aplicativo Shifts para sua organização no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)