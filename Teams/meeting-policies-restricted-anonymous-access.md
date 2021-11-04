---
title: Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários
author: serdars
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Saiba como remover a política de reunião RestrictedAnonymousAccess Teams de usuários em sua organização.
ms.openlocfilehash: e1b5cc0f72419bc17fcca34e3a586ef781f93c93
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766130"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários

[As políticas de](meeting-policies-overview.md) reunião Microsoft Teams são usadas para controlar os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas pelos usuários em sua organização. 

Teams inclui uma política interna chamada RestrictedAnonymousAccess, que contém configurações pré-definidas que incluem a restrição de usuários anônimos de iniciar uma reunião. (Usuários anônimos são usuários que não foram autenticados.) As configurações predefinidas na política de reunião não podem ser editadas ou alteradas pelos administradores.

Este artigo mostra como usar o PowerShell para remover a política de reunião RestrictedAnonymousAccess dos usuários que são atribuídos a essa política. Para saber mais sobre como gerenciar o Teams usando o PowerShell, consulte Teams visão geral do [PowerShell.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Antes de começar

Instale e conecte-se ao [módulo Skype for Business PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell). Para obter orientações passo a passo, consulte [Install Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obter as Teams de política de reunião da sua organização

Execute o seguinte para obter as Teams de reunião da sua organização.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

Neste exemplo, a saída a seguir é retornada, o que mostra que dois usuários são atribuídos à política de reunião RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Desaigne a política de reunião RestrictedAnonymous dos usuários

Para remover a política de reunião RestrictedAnonymous dos usuários, você pode usar o cmdlet [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) se tiver um pequeno número de usuários (por exemplo, menos de 100 usuários). Se você tiver um grande número de usuários (por exemplo, mais de 100 usuários), será mais eficiente usar o cmdlet  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar uma operação em lotes.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Use o cmdlet Grant-CsTeamsMeeting Policy

Execute o seguinte para remover a política de reunião RestrictedAnonymous dos usuários.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Usar o cmdlet New-CsBatchPolicyAssignmentOperation

Com [a atribuição](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)de política em lote, o número máximo de usuários para os quais você pode remover ou atualizar políticas é 5.000 por vez. Por exemplo, se você tiver mais de 5.000 usuários, precisará enviar vários lotes. Para melhores resultados, não envie vários lotes por vez. Permitir que lotes concluam o processamento antes de enviar mais lotes.

> [!NOTE]
> O cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) está no módulo Teams PowerShell. Antes de seguir estas etapas, instale e conecte-se ao [módulo Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Para obter orientações passo a passo, consulte [Install Microsoft Teams PowerShell](teams-powershell-install.md).

Execute os seguintes comandos para remover a política de reunião RestrictedAnonymousAccess de um lote de usuários.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obter o status da atribuição em lotes

Cada atribuição em lotes retorna uma ID de operação, que você pode usar para rastrear o progresso e o status das atribuições e identificar quaisquer falhas que possam ocorrer. Por exemplo, execute o seguinte:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Certifique-se **de que ErrorCount** seja **0** (zero) e **OverallStatus** seja **Concluído**.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)