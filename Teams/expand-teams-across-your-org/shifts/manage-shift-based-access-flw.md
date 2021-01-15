---
title: Gerenciar o acesso baseado em turnos para trabalhadores da linha de frente no Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar o acesso baseado em turnos no Teams para trabalhadores da linha de frente em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b73fe9b3c4b39e7d3fa7b31427f563c47e5a737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823011"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Gerenciar o acesso baseado em turnos para trabalhadores da linha de frente no Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi retirado. Estamos criando recursos do StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo Turnos para gerenciamento de agendamento e recursos adicionais serão incluídos ao longo do tempo. O StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub é exibida uma mensagem direcionando-a para baixar o Teams. Para saber mais, confira [o Microsoft StaffHub foi retirado.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview"></a>Visão Geral

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A presença no Microsoft Teams indica a disponibilidade e o status atuais do usuário para outros usuários. A presença de Trabalhadores de Linha de Frente geralmente é menos previsível do que outras equipes, pois suas horas de trabalho normalmente não são as mesmas a cada dia. Como administrador, você pode configurar o Teams para mostrar um conjunto de estados de presença baseados em turnos para os Trabalhadores da Linha de Frente em sua organização para indicar quando eles estão no turno de folga.

Esses estados de presença baseados em turnos indicam marca de seleção verde sólido, indica No turno no turno , Círculo cinza com x, indica Fora do turno fora do turno , círculo vermelho sólido, indica Ocupado Ocupado são separados do conjunto padrão de estados de presença no &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Com esses dois conjuntos de estados de presença, você pode configurar experiências diferentes para as pessoas em sua organização com base em sua função.

Com o acesso baseado em turnos, você pode gerenciar o acesso ao Teams quando os Trabalhadores da Linha de Frente estão fora do turno. Por exemplo, você pode definir o Teams para exibir uma mensagem que os Trabalhadores da Linha de Frente devem confirmar antes de poder usar o Teams quando não estão em um turno agendado.  

## <a name="scenario"></a>Cenário

Veja um exemplo de como sua organização pode gerenciar o acesso baseado em turnos.

Você tem trabalhadores da linha de frente em sua organização que só devem ser pagos por horas em que trabalham em um turno agendado e aprovado pelo gerente. Eles não devem ser pagos pelo tempo gasto trabalhando fora de um turno agendado, o que inclui o uso do aplicativo Teams. Você configura uma mensagem personalizada que diz "Seu tempo no Teams quando está fora do turno não contará para as horas de pagamento", que é exibida quando os funcionários da linha de frente tentam acessar o Teams quando estão fora do turno. Se eles optarem por usar o Teams, eles clicarão em **Aceitar** com o entendimento de que não serão pagos por esse tempo.

Você também tem funcionários de informações em sua organização com salários e que não trabalham em turnos. Você configura seus funcionários de informações para usar os estados de presença padrão no Teams, ao mesmo tempo em que dá a seus trabalhadores de linha de frente a presença baseada em turnos.

## <a name="shift-based-presence-states"></a>Estados de presença baseados em turnos

Aqui estão os estados de presença baseados em turnos.

|Aplicativo configurado |Usuário configurado  |Mais informações  |
|---------|---------|---------|
|![Marca de seleção verde sólido, indica No turno](../../media/flw-presence-on-shift.png) No turno     |         |Definido automaticamente no início de um turno         |
|![Círculo cinza com x, indica Off shift](../../media/flw-presence-off-shift.png) Fora do turno     |         |Definido automaticamente no final de um turno         |
|![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Definido automaticamente. Também pode ser definido manualmente quando o Firstline Worker está no turno.|

## <a name="off-shift-access-to-teams"></a>Acesso fora do turno ao Teams

Esse recurso permite que você gerencie o acesso ao Teams quando os Funcionários da Linha de Frente estão fora do turno. Você pode definir o Teams para exibir uma mensagem para Os Trabalhadores da Linha de Frente se eles acessarem o Teams quando estão fora do turno. Os trabalhadores da linha de frente **devem clicar em Aceitar** para confirmar a mensagem antes que possam usar o Teams.

Você pode usar a mensagem padrão, escolher entre um conjunto de mensagens pré-definidas ou personalizar a mensagem para exibir qualquer texto que você quiser. Esta é a mensagem padrão:

![Captura de tela da mensagem padrão](../../media/shifts-presence-message.png)

Você também pode definir a frequência quando a mensagem é exibida e definir um período de carência entre o início do primeiro turno ou o fim do último turno e quando o acesso ao Teams é restrito.

## <a name="manage-shift-based-access"></a>Gerenciar acesso baseado em turnos

Como administrador, você usa políticas para controlar a presença baseada em turnos para trabalhadores da linha de frente em sua organização. Você gerencia essas políticas usando os seguintes cmdlets do PowerShell:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Use o cmdlet New-CsTeamsShiftsPolicy para criar uma nova política, definir as configurações de política que você deseja e, em seguida, use o cmdlet Grant-CsTeamsShiftsPolicy para atribuir a política aos usuários.

Aqui estão alguns exemplos. Para obter informações detalhadas sobre cada configuração de política e parâmetro, incluindo a lista de mensagens de deslocamento predefinidos que você pode escolher, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Exemplo 1

Neste exemplo, criamos uma nova política chamada Mensagem Padrão de Acesso ao Off Shift Teams. Nesta política, a presença baseada em turnos é 2013 e a mensagem padrão é exibida sempre que um usuário atribuído a essa política acessa o Teams quando está fora do turno. O usuário pode usar o Teams fora do turno se aceitar a mensagem e o período de carência entre o início do primeiro turno ou o fim do último turno e quando o acesso é restrito é de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Exemplo 2 

Neste exemplo, criamos uma nova política chamada Mensagem Personalizada de Acesso ao Off Shift Teams. Nesta política, a presença baseada em turnos é 2013 e uma mensagem personalizada é exibida sempre que um usuário atribuído a essa política acessa o Teams quando está fora do turno. O usuário poderá usar o Teams quando estiver fora do turno se aceitar a mensagem e o período de carência entre o início do primeiro turno ou o fim do último turno e quando o acesso for restrito for de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para saber mais, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Exemplo 3

Neste exemplo, criamos uma nova política chamada Mensagem de Acesso do Off Shift Teams1. Nesta política, a presença baseada em turnos é ativa e a seguinte mensagem predefinida é exibida sempre que um usuário atribuído a essa política acessa o Teams quando está fora do turno.

  "Seu empregador não autoriza ou aprova o uso de sua rede, aplicativos, sistemas ou ferramentas por funcionários não isentos ou por hora durante suas horas de não trabalho. Ao aceitar, você reconhece que o uso do Teams fora do turno não está autorizado e não será compensado." 

O usuário pode usar o Teams fora do turno se aceitar a mensagem, e o período de carência entre o início do primeiro turno ou o fim do último turno e quando o acesso é restrito é de três minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Exemplo 4

Neste exemplo, atribuímos uma política chamada Desatribuição de Mensagem Personalizada de Acesso do Teams a um usuário chamado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o aplicativo Shifts para sua organização no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)
