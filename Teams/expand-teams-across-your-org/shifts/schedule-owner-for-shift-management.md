---
title: Gerenciar proprietários de agendamento para gerenciamento de turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Saiba como gerenciar proprietários de turnos para gerenciamento de agendamento. Você pode definir uma política para elevar a permissão de um membro da equipe para um proprietário de agendamento.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12cf33f193e7f1d1a976e5cde8612df19108cb69
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288629"
---
# <a name="schedule-owner-for-shift-management"></a>Agendar Proprietário para gerenciamento de turnos

## <a name="overview"></a>Visão Geral

O recurso Agendar Proprietário permite que você eleve as permissões de um membro da equipe para que ele possa gerenciar agendas sem tornar o funcionário um proprietário de equipe. Com as permissões Agendar Proprietário, um funcionário pode gerenciar a agenda de sua equipe sem poder modificar quaisquer outras propriedades de equipe, como atualização, edição ou exclusão de canais de equipe.

O que um usuário com permissões de proprietário de agendamento pode fazer?

- Crie, edite e publique agendas para gerenciar as atribuições de turno da equipe.
- Exibir e aprovar solicitações de turno, incluindo solicitações para trocar turnos e fazer turnos abertos.
- Gerencie configurações em Shifts para habilitar determinados recursos para a equipe.
- Exibir e modificar o quadro de horários de sua equipe para processar as folhas de pagamento dos funcionários.

## <a name="why-schedule-owner"></a>Por que Agendar Proprietário?

Sem o recurso Agendar Proprietário, as funções comerciais diárias podem ser interrompidas. Embora o proprietário da equipe ajude a executar a equipe, ele pode não ser necessariamente o responsável pelo agendamento do dia a dia. Nesse caso, transferir apenas a responsabilidade de gerenciamento de agendamento para outro membro da equipe simplifica as operações diárias dentro da equipe e elimina a confusão de dois membros da equipe que têm os mesmos privilégios de acesso.

## <a name="scenario"></a>Cenário

Veja um exemplo de como sua organização pode usar o recurso Agendar Proprietário.

Você trabalha em uma organização grande em que os gerentes de departamento reportam diretamente ao gerente da loja. O gerente da loja tem mais autoridade em sua empresa e é o proprietário da equipe em Shifts. Os gerentes de departamento, por outro lado, só são adicionados a Shifts como membros da equipe. Embora os gerentes de loja tenham mais antiguidades do que gerentes de departamento, faz mais sentido para os gerentes de departamento lidarem com o agendamento do dia a dia dos funcionários da equipe.

*Sem o Proprietário do Agendamento*, os gerentes de departamento devem receber os mesmos privilégios que o proprietário da equipe. Recentemente, os gerentes de departamento têm mudado informações e mudado o nome dos canais, e isso causou complicações com o trabalho do gerente da loja. O gerente da loja deseja que os gerentes de departamentos sejam capazes de organizar seus cronogramas, mas não quer que eles sejam capazes de alterar qualquer outra coisa na equipe, fora de Shifts.

*Com o Proprietário do* Agendamento, os gerentes de departamento podem receber privilégios de agendamento, sem quaisquer outros privilégios de proprietário da equipe.

## <a name="manage-schedule-ownership"></a>Gerenciar a propriedade de agendamento

Como administrador, você usa políticas para controlar a propriedade de gerenciamento de agendamento em sua organização. Você gerencia essas políticas usando os seguintes cmdlets do PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Exemplo 1

Aqui, criamos uma nova política chamada ScheduleOwnerPolicy com o recurso Agendar Proprietário ligado.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Exemplo 2

Neste exemplo, atribuímos uma política chamada ScheduleOwnerPolicy a um usuário chamado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar o aplicativo Shifts para sua organização no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gerenciar o acesso baseado em turnos para os funcionários de linha de frente Teams](manage-shift-based-access-flw.md) 
