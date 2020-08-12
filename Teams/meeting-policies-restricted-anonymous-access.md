---
title: Remover a política de reunião do RestrictedAnonymousAccess Teams dos usuários
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Saiba como remover a política de reunião do teams RestrictedAnonymousAccess dos usuários em sua organização.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640967"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Remover a política de reunião do RestrictedAnonymousAccess Teams dos usuários

[As políticas de reunião](meeting-policies-in-teams.md) no Microsoft Teams são usadas para controlar os recursos que estão disponíveis para os participantes da reunião em reuniões agendadas pelos usuários da sua organização. 

O Teams inclui uma política interna chamada RestrictedAnonymousAccess, que contém configurações predefinidas que incluem a restrição de usuários anônimos de iniciar uma reunião. (Usuários anônimos são usuários que não foram autenticados.) As configurações predefinidas na política da reunião não podem ser editadas nem alteradas por administradores.

Este artigo mostra como usar o PowerShell para remover a política de reunião do RestrictedAnonymousAccess dos usuários atribuídos a essa política. Para saber mais sobre como gerenciar o Microsoft Teams usando o PowerShell, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

## <a name="before-you-start"></a>Antes de começar

Instale e conecte-se ao [módulo do PowerShell do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366). Para obter orientação passo a passo, confira [instalar o Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obter as atribuições de política de reunião do teams para sua organização

Execute o seguinte para obter as atribuições de política de reunião do teams para sua organização.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

Neste exemplo, a saída a seguir é retornada, o que mostra que dois usuários recebem a política de reunião do RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Cancelar a atribuição da política de reunião do RestrictedAnonymous de usuários

Para remover a política de reunião do RestrictedAnonymous dos usuários, você pode usar o cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) se tiver um pequeno número de usuários (por exemplo, menos de 100 usuários). Se você tiver um grande número de usuários (por exemplo, mais de 100 usuários), é mais eficiente usar o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) para enviar uma operação em lotes.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Usar o cmdlet da política Grant-CsTeamsMeeting

Execute o seguinte para remover a política de reunião do RestrictedAnonymous dos usuários.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Usar o cmdlet New-CsBatchPolicyAssignmentOperation

Com a [atribuição de política em lotes](assign-policies.md#assign-a-policy-to-a-batch-of-users), o número máximo de usuários para os quais você pode remover ou atualizar políticas é de 5.000 de cada vez. Por exemplo, se você tiver mais de 5.000 usuários, será necessário enviar vários lotes. Para obter melhores resultados, não envie vários lotes de cada vez. Permitir que os lotes concluam o processamento antes de enviar mais lotes.

> [!NOTE]
> O cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) está no módulo do PowerShell Teams. Antes de seguir estas etapas, instale e conecte-se ao [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Para obter orientação passo a passo, confira [instalar o Microsoft Teams PowerShell](teams-powershell-install.md).

Execute os comandos a seguir para remover a política de reunião do RestrictedAnonymousAccess de um lote de usuários.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obter o status da atribuição em lotes

Cada atribuição de lote retorna uma ID de operação, que você pode usar para acompanhar o andamento e o status das tarefas e identificar quaisquer falhas que possam ocorrer. Por exemplo, execute o seguinte:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Verifique se o **ErrorCount** é **0** (zero) e se **OverallStatus** está **concluído**.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas a seus usuários no Teams](assign-policies.md)
