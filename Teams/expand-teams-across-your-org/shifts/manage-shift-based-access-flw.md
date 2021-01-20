---
title: Gerenciar o acesso baseado em Shift para trabalhadores do Frontline no Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar o acesso baseado em Shift no Teams para trabalhadores do Frontline em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 437902136bf72685dabf5bd6359dd6221c7467de
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909465"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gerenciar o acesso baseado em Shift para trabalhadores do Frontline no Microsoft Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [o Microsoft StaffHub foi desativado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Visão Geral

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A presença no Microsoft Teams indica a disponibilidade e o status do usuário atual para outros usuários. A presença de funcionários do Frontline geralmente é menos previsível do que a outra equipe, pois as horas de trabalho normalmente não são iguais todos os dias. Como administrador, você pode configurar o Microsoft Teams para mostrar um conjunto de Estados de presença baseada em Shift para que os trabalhadores do Frontline em sua organização indiquem quando eles estão ativados e desligados.

Esses Estados de presença com base em Shift indicam a &mdash; ![ marca de seleção verde estável, indica que, em Shift, ](../../media/flw-presence-on-shift.png) **em Shift**, ![ círculo cinza com x, indica o deslocamento de SHIFT ](../../media/flw-presence-off-shift.png) **desligado**, ![ círculo vermelho sólido, indica ocupado ocupado ](../../media/flw-presence-busy.png)  &mdash; são separados do [conjunto padrão de Estados de presença](../../presence-admins.md) no Microsoft Teams. Com esses dois conjuntos de Estados de presença, você pode configurar experiências diferentes para as pessoas em sua organização com base em suas funções.

Com o acesso baseado em Shift, você pode gerenciar o acesso às equipes quando os funcionários do Frontline estiverem fora do turno. Por exemplo, você pode definir o Teams para exibir uma mensagem que os funcionários do Frontline devem confirmar antes de poderem usar o Microsoft Teams quando não estiverem em um turno programado.  

## <a name="scenario"></a>Cenário

Veja um exemplo de como sua organização pode gerenciar o acesso baseado em Shift.

Você tem funcionários do Frontline em sua organização que devem ser pagos apenas por horas em que eles trabalham em um turno que seus gerentes agendados e aprovados. Eles não devem ser pagos por tempo gasto trabalhando fora de um turno agendado, que inclui o uso do aplicativo Teams. Você configura uma mensagem personalizada que diz "seu tempo na equipe quando o turno está desligado não conta em relação a contas a pagar", que é exibido quando os funcionários do Frontline tentam acessar o Microsoft Teams quando estão fora do turno. Se eles escolherem usar o Microsoft Teams, clique em **aceito** com o entendimento de que eles não serão pagos durante esse período.

Você também tem operadores de informações em sua organização que estão salários e quem não funcionam turnos. Você configura seus operadores de informações para usar os Estados de presença padrão no Teams e, ao mesmo tempo, oferecer aos trabalhadores do Frontline a presença baseada em turno.

## <a name="shift-based-presence-states"></a>Estados de presença baseados em Shift

Estes são os Estados de presença baseados em Shift.

|Aplicativo configurado |Usuário configurado  |Mais informações  |
|---------|---------|---------|
|![Marca de seleção verde estável, indica no turno](../../media/flw-presence-on-shift.png) No turno     |         |Definido automaticamente no início de um turno         |
|![Círculo cinza com x, indica o turno](../../media/flw-presence-off-shift.png) Desativar Shift     |         |Definido automaticamente no fim de um turno         |
|![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Definido automaticamente. Também pode ser definido manualmente quando o trabalhador do Frontline está em turno.|

## <a name="off-shift-access-to-teams"></a>Desativar o acesso ao Microsoft Teams

Esse recurso permite que você gerencie o acesso ao Teams quando os funcionários do Frontline estão fora do turno. Você pode definir o Microsoft Teams para exibir uma mensagem para trabalhadores do Frontline se eles acessarem equipes quando estiverem fora do turno. Os funcionários do Frontline devem clicar em **aceito** para confirmar a mensagem antes de poderem usar o Microsoft Teams.

Você pode usar a mensagem padrão, escolher entre um conjunto de mensagens predefinidas ou personalizar a mensagem para exibir qualquer texto desejado. Aqui está a mensagem padrão:

![Captura de tela da mensagem padrão](../../media/shifts-presence-message.png)

Você também pode definir a frequência quando a mensagem for exibida e definir um período de cortesia entre quando o primeiro turno começar ou o último turno terminar e quando o acesso às equipes for restrito.

## <a name="manage-shift-based-access"></a>Gerenciar o acesso baseado em Shift

Como administrador, você usa políticas para controlar a presença baseada em Shift para trabalhadores do Frontline em sua organização. Para gerenciar essas políticas, use os seguintes cmdlets do PowerShell:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Use o cmdlet New-CsTeamsShiftsPolicy para criar uma nova política, definir as configurações de política desejadas e usar o cmdlet Grant-CsTeamsShiftsPolicy para atribuir a política a usuários.

Aqui estão alguns exemplos. Para obter informações detalhadas sobre cada configuração de política e parâmetro, incluindo a lista de mensagens de turno predefinidas que você pode escolher, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Exemplo 1

Neste exemplo, criamos uma nova política chamada desativar a mensagem padrão do Access Teams Access. Nesta política, a presença baseada em Shift está ativada e a mensagem padrão é exibida sempre que um usuário atribuído essa política acessa as equipes quando está fora do turno. O usuário poderá usar o Microsoft Teams quando ele aceitar a mensagem e o período de cortesia entre quando o primeiro turno começar ou o último turno terminar e quando o acesso for restrito é de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use o parâmetro **ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens predefinidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Exemplo 2 

Neste exemplo, criamos uma nova política chamada desativar a mensagem personalizada do Access Teams Access. Nesta política, a presença baseada em Shift está ativada e uma mensagem personalizada é exibida sempre que um usuário atribuído essa política acessa o Microsoft Teams quando está fora do turno. O usuário poderá usar o Microsoft Teams quando ele aceitar a mensagem, e o período de cortesia entre quando o primeiro turno começar ou o último turno terminar e quando o acesso for restrito for de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use o parâmetro **ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para saber mais, confira [novo – CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Exemplo 3

Neste exemplo, criamos uma nova política chamada desligada do Access Teams Access message1. Nesta política, a presença baseada em Shift está ativada e a seguinte mensagem predefinida é exibida toda vez que um usuário atribuído essa política acessa as equipes quando está fora do turno.

  "Seu empregador não autoriza ou aprova o uso da rede, dos aplicativos, dos sistemas ou das ferramentas por funcionários não isentos ou por hora, durante suas horas de folga. Ao aceitar, você reconhece que o uso do Microsoft Teams fora do turno não é autorizado e não será remunerado. " 

O usuário poderá usar o Microsoft Teams quando ele aceitar a mensagem, e o período de cortesia entre quando o primeiro turno começar ou o último turno terminar e quando o acesso for restrito é de três minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use o parâmetro **ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens predefinidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Exemplo 4

Neste exemplo, atribuímos uma política chamada desativar mensagem personalizada do Access Teams para um usuário chamado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o aplicativo Shifts para sua organização no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)
