---
title: Gerenciar o acesso baseado em turnos para Trabalhadores de Linha de Frente no Teams
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
ms.openlocfilehash: 437902136bf72685dabf5bd6359dd6221c7467de
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909465"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gerenciar o acesso baseado em turnos para Trabalhadores de Linha de Frente no Teams

> [!IMPORTANT]
> A partir de 30 de junho de 2020, o Microsoft StaffHub foi retirado. Estamos criando recursos do StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo Shifts para gerenciamento de cronogramas e recursos adicionais serão incluídos ao longo do tempo. O StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-a para baixar o Teams. Para saber mais, confira [o Microsoft StaffHub foi retirado.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview"></a>Visão Geral

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

A presença no Microsoft Teams indica a disponibilidade atual e o status de um usuário para outros usuários. A presença dos Trabalhadores da Linha de Frente geralmente é menos previsível do que a de outros funcionários, pois suas horas de trabalho normalmente não são iguais a cada dia. Como administrador, você pode configurar o Teams para mostrar um conjunto de estados de presença baseados em turnos para os Trabalhadores de Linha de Frente em sua organização indicarem quando eles estão dentro e fora do turno.

Esses estados de presença baseados em turnos Marca de seleção verde sólido, indica No turno No turno, Círculo cinza com x, indica Deslocamento fora do turno, Círculo sólido vermelho, indica Que Ocupado Ocupado está separado do conjunto padrão de estados de presença no &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Com esses dois conjuntos de estados de presença, você pode configurar experiências diferentes para as pessoas em sua organização com base em suas funções.

Com o acesso baseado em turnos, você pode gerenciar o acesso ao Teams quando os Frontline Workers estão fora do turno. Por exemplo, você pode definir o Teams para exibir uma mensagem que os Trabalhadores da Linha de Frente devem confirmar antes de usar o Teams quando não estão em um turno agendado.  

## <a name="scenario"></a>Cenário

Veja um exemplo de como sua organização pode gerenciar o acesso baseado em turnos.

Você tem Trabalhadores de Linha de Frente em sua organização que só devem ser pagos por horas em que trabalham em um turno que o gerente agendou e aprovou. Eles não devem ser pagos pelo tempo gasto trabalhando fora de um turno agendado, o que inclui o uso do aplicativo Teams. Você configura uma mensagem personalizada que diz "Seu tempo no Teams quando está fora do turno não conta para horas pagáveis", que é exibida quando os Trabalhadores da Linha de Frente tentam acessar o Teams quando estão fora do turno. Se eles optarem por usar o Teams, clicarão em **Aceitar** com a compreensão de que não serão pagos desta vez.

Você também tem trabalhadores da informação em sua organização que estão com salários e que não trabalham nos turnos. Configure seus trabalhadores da informação para usar os estados de presença padrão no Teams e, ao mesmo tempo, dar aos seus Trabalhadores da Linha de Frente uma presença baseada em turnos.

## <a name="shift-based-presence-states"></a>Estados de presença baseados em turnos

Aqui estão os estados de presença baseados em turnos.

|Aplicativo configurado |Usuário configurado  |Mais informações  |
|---------|---------|---------|
|![Marca de seleção verde sólido, indica No turno](../../media/flw-presence-on-shift.png) No turno     |         |Definir automaticamente no início de um turno         |
|![Círculo cinza com x, indica Folga no turno](../../media/flw-presence-off-shift.png) Folga no turno     |         |Definir automaticamente no final de um turno         |
|![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo vermelho, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Definido automaticamente. Também pode ser definido manualmente quando o Trabalhador da Linha de Frente está no turno.|

## <a name="off-shift-access-to-teams"></a>Acesso fora do turno ao Teams

Esse recurso permite gerenciar o acesso ao Teams quando os Trabalhadores da Linha de Frente estão fora do turno. Você pode definir o Teams para exibir uma mensagem para os Trabalhadores de Linha de Frente se eles acessarem o Teams quando estão fora do turno. Os Trabalhadores da Linha de Frente **devem clicar em Aceitar** para confirmar a mensagem antes que possam usar o Teams.

Você pode usar a mensagem padrão, escolher entre um conjunto de mensagens predefinidas ou personalizar a mensagem para exibir qualquer texto que quiser. Esta é a mensagem padrão:

![Captura de tela da mensagem padrão](../../media/shifts-presence-message.png)

Você também pode definir a frequência quando a mensagem é exibida e definir um período de graça entre o início do primeiro turno ou o último turno e quando o acesso ao Teams estiver restrito.

## <a name="manage-shift-based-access"></a>Gerenciar o acesso baseado em turnos

Como administrador, você usa políticas para controlar a presença baseada em turnos para Frontline Workers em sua organização. Você gerencia essas políticas usando os seguintes cmdlets do PowerShell:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Use o cmdlet New-CsTeamsShiftsPolicy para criar uma nova política, definir as configurações de política que você deseja e use o cmdlet Grant-CsTeamsShiftsPolicy para atribuir a política aos usuários.

Aqui estão alguns exemplos. Para obter informações detalhadas sobre cada configuração de política e parâmetro, incluindo a lista de mensagens de turnos fora predefinida que você pode escolher, consulte [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Exemplo 1

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Default Message. Nesta política, a presença baseada em turnos é 2010 e a mensagem padrão é exibida sempre que um usuário que recebe essa política acessa o Teams quando está fora do turno. O usuário pode usar o Teams quando estiver fora do turno se aceitar a mensagem, e o período de graça entre o início do primeiro turno ou o último turno terminar e quando o acesso for restrito for de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Exemplo 2 

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Custom Message. Nesta política, a presença baseada em turnos é 2010 e uma mensagem personalizada é exibida sempre que um usuário que recebe essa política acessa o Teams quando está fora do turno. O usuário pode usar o Teams quando estiver fora do turno se aceitar a mensagem e o período de carência entre o início do primeiro turno ou o último turno terminar e quando o acesso for restrito for de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para saber mais, consulte [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Exemplo 3

Neste exemplo, criamos uma nova política chamada Off Shift Teams Access Message1. Nesta política, a presença baseada em turnos é ativa e a seguinte mensagem predefinida é exibida sempre que um usuário que recebe essa política acessa o Teams quando está fora do turno.

  "Seu empregador não autoriza nem aprova o uso de sua rede, aplicativos, sistemas ou ferramentas por funcionários não isentos ou por hora durante suas horas de trabalho. Ao aceitar, você reconhece que seu uso do Teams enquanto estiver fora do turno não está autorizado e você não será compensado." 

O usuário pode usar o Teams quando estiver fora do turno se aceitar a mensagem e o período de graça entre o início do primeiro turno ou o último turno terminar e quando o acesso for restrito for de três minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use o **parâmetro ShiftNoticeMessageType** para definir a mensagem que você deseja exibir. Para ver uma lista das mensagens pré-definidas que você pode escolher para esse parâmetro, consulte [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Exemplo 4

Neste exemplo, atribuímos uma política chamada Off Shift Teams Access Custom Message a um usuário chamado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o aplicativo Shifts para sua organização no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)
