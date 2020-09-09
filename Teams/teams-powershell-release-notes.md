---
title: Notas de versão do Microsoft Teams PowerShell
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba mais sobre as alterações mais recentes no PowerShell do teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80a1a887ea1db964c8d9b9fe55f144208967f37d
ms.sourcegitcommit: 207c58563b7b2aba274b067cf64242abd7a33c2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405808"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notas de versão do Microsoft Teams PowerShell

Esta página fornece o log de alterações mais recente do PowerShell do teams para disponibilidade geral e lançamentos de visualização pública.

## <a name="release-notes"></a>Notas de versão

> [!NOTE]
> **-a visualização** na coluna versão abaixo representa as atualizações para a visualização pública do teams PowerShell.

| Data | Versão | Actualiza |
|------- | -------------------- | ------------------------------ |
| Setembro de 2020 | [1.1.5-Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integração do conector do Skype for Business Online</li> |
| De julho de 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>[Cmdlets de atribuição de política de grupo](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group) adicionados</li> |
| De junho de 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integração do conector do Skype for Business Online<li>Otimizações de get-Team<li>Maior confiabilidade</li> |
| De junho de 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Precarregamento de cmdlet adicionado<li>Otimizações do .NET Framework</li>   |
| Abril de 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Assinatura Authenticode e assembly<li>Get-CsPolicyPackage adicionado<li>Get-CsUserPolicyPackage adicionado<li>Get-CsUserPolicyPackageRecommendation adicionado<li>Concessão adicionada-CsUserPolicyPackage<li>Adicionar novo-CsBatchPolicyPackageAssignmentOperation<li>Conjunto adicionado-TeamArchivedState<li>Conjunto adicionado-TeamPicture<li>Get-TeamHelp removido</li>  |
| Março de 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Adicionar novo-CsBatchPolicyAssignmentOperation</li> |
| Fevereiro de 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Otimizações de get-Team</li>  |

### <a name="cmdlet-availability"></a>Disponibilidade do cmdlet

> [!NOTE]
> A lista na tabela a seguir inclui cmdlets que são parte nativa do módulo do teams PowerShell. Os cmdlets do teams no[módulo do conector do Kype for Business online](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) não são exibidos. No entanto, como os cmdlets são migrados nativamente para o Teams PowerShell, vamos adicioná-los a essa tabela.

| Cmdlet | Disponível no modo de visualização pública | Disponível no GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sim | **Não** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Sim | Sim |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sim | **Não**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sim | Sim |
| [Desconectar-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sim | Sim |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sim | Sim |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Sim | **Não** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Sim | **Não** |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Sim | Sim |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Sim | Sim |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Sim | Sim |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Sim | Sim |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Sim | Sim |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Sim | Sim|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Sim | **Não** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Sim | Sim |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Sim | Sim |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Sim | **Não** |
| [Grant CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Sim | Sim |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Sim | Sim |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Sim | Sim |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Sim | Sim |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Sim | **Não** |
| [New-Team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Sim | Sim |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Sim | Sim |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Sim | Sim |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Sim | Sim |
| [Remover-equipe](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Sim | Sim |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Sim | Sim |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Sim | **Não** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Sim | Sim |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Sim | **Não** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Sim | **Não**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Sim | Sim |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Sim | **Não** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Sim | Sim |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Sim | Sim |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Sim | Sim |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Sim | Sim |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Sim | Sim |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Sim | **Não** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Sim | **Não** |

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Instalando o Microsoft Teams PowerShell](teams-powershell-install.md)

[Gerenciando equipes com o PowerShell do teams](teams-powershell-managing-teams.md)

[Referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
