---
title: Gerenciar o acesso baseado em Shift para trabalhadores iniciais no Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar o acesso baseado em Shift nas equipes para trabalhadores iniciantes em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ec470422e402da07171bef627d1592c73d6c12f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514128"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Gerenciar o acesso baseado em Shift para trabalhadores iniciais no Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [o Microsoft StaffHub foi desativado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Visão geral

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A presença no Microsoft Teams indica a disponibilidade e o status do usuário atual para outros usuários. A presença de funcionários iniciais geralmente é menos previsível do que a outra equipe, pois as horas de trabalho normalmente não são iguais todos os dias. Como administrador, você pode configurar o Microsoft Teams para mostrar um conjunto de Estados de presença baseada em Shift para que os primeiros funcionários de sua organização indiquem quando eles estão ativados e desligados.

Esses Estados de presença com base em Shift indicam a &mdash; ![ marca de seleção verde estável, indica que, em Shift, ](../../media/flw-presence-on-shift.png) **em Shift**, ![ círculo cinza com x, indica o deslocamento de SHIFT ](../../media/flw-presence-off-shift.png) **desligado**, ![ círculo vermelho sólido, indica ocupado ocupado ](../../media/flw-presence-busy.png) **Busy** &mdash; são separados do [conjunto padrão de Estados de presença](../../presence-admins.md) no Microsoft Teams. Com esses dois conjuntos de Estados de presença, você pode configurar experiências diferentes para as pessoas em sua organização com base em suas funções.

Com o acesso baseado em Shift, você pode gerenciar o acesso às equipes quando os trabalhadores de primeira mão estiverem fora do turno. Por exemplo, você pode definir o Teams para exibir uma mensagem que os funcionários da primeira pessoa devem confirmar antes de poderem usar o Teams quando não estiverem em um turno programado.  

## <a name="scenario"></a>Cenário

Veja um exemplo de como sua organização pode gerenciar o acesso baseado em Shift.

Você tem trabalhadores de primeira mão em sua organização que devem ser pagos apenas por horas que eles trabalham em um turno que seus gerentes agendados e aprovados. Eles não devem ser pagos por tempo gasto trabalhando fora de um turno agendado, que inclui o uso do aplicativo Teams. Você configura uma mensagem personalizada que diz "seu tempo na equipe quando o turno desligado não contará em relação a contas a pagar", que é exibido quando trabalhadores de primeira tentativa de acessar o Microsoft Teams quando estão fora do turno. Se eles escolherem usar o Microsoft Teams, clique em **aceito** com o entendimento de que eles não serão pagos durante esse período.

Você também tem operadores de informações em sua organização que estão salários e quem não funcionam turnos. Você configura seus operadores de informações para usar os Estados de presença padrão no Teams enquanto dá ao seu primeiro trabalho presença baseada em Shift.

## <a name="shift-based-presence-states"></a>Estados de presença baseados em Shift

Estes são os Estados de presença baseados em Shift.

|Aplicativo configurado |Usuário configurado  |Mais informações  |
|---------|---------|---------|
|![Marca de seleção verde estável, indica no turno](../../media/flw-presence-on-shift.png) No turno     |         |Definido automaticamente no início de um turno         |
|![Círculo cinza com x, indica o turno](../../media/flw-presence-off-shift.png) Desativar Shift     |         |Definido automaticamente no fim de um turno         |
|![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Definido automaticamente. Também pode ser definido manualmente quando o trabalhador da primeira está em turno.|

## <a name="off-shift-access-to-teams"></a>Desativar o acesso ao Microsoft Teams

Esse recurso permite que você gerencie o acesso às equipes quando os trabalhadores de primeira mão estiverem fora do turno. Você pode definir o Microsoft Teams para exibir uma mensagem para trabalhadores de primeira mão se acessar o Teams quando estiver fora do turno. Os funcionários de primeira mão devem clicar em **aceito** para confirmar a mensagem antes de poderem usar o Teams.

Você pode usar a mensagem padrão, escolher entre um conjunto de mensagens predefinidas ou personalizar a mensagem para exibir qualquer texto desejado. Aqui está a mensagem padrão:

![Captura de tela da mensagem padrão](../../media/shifts-presence-message.png)

Você também pode definir a frequência quando a mensagem for exibida e definir um período de cortesia entre quando o primeiro turno começar ou o último turno terminar e quando o acesso às equipes for restrito.

## <a name="manage-shift-based-access"></a>Gerenciar o acesso baseado em Shift

Como administrador, você usa políticas para controlar a presença baseada em Shift para trabalhadores de primeira mão em sua organização. Para gerenciar essas políticas, use os seguintes cmdlets do PowerShell:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Use o cmdlet New-CsTeamsShiftsPolicy para criar uma nova política, definir as configurações de política desejadas e usar o cmdlet Grant-CsTeamsShiftsPolicy para atribuir a política a usuários.

Veja alguns exemplos. Para obter informações detalhadas sobre cada configuração de política e parâmetro, incluindo a lista de mensagens de turno predefinidas que você pode escolher, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

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
