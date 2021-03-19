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
description: Saiba mais sobre as alterações mais recentes no Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef78d1a6be92ba3d7f4c84ce8012f84f40e58e96
ms.sourcegitcommit: 71b9b5ec80014bd25758493bc06d633c4eac735c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50867070"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notas de versão do Microsoft Teams PowerShell

Esta página fornece o log de alterações mais recente do Teams PowerShell para versões de Disponibilidade Geral e Visualização Pública.

## <a name="release-notes"></a>Notas de versão

> [!NOTE]
> **-preview** na coluna versão abaixo representa atualizações para a visualização pública do PowerShell do Teams.

| Data | Versão | Atualizações |
|------- | -------------------- | ------------------------------ |
| Março de 2021 | [2.0](https://www.powershellgallery.com/packages/MicrosoftTeams/) | <li>Connect-MicrosoftTeams é o ponto de entrada para todos os cmdlets.</li><li>New-csOnlineSession não é mais disponível. Ele foi substituído por Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection não é mais necessário. O recurso foi implementado de forma nativa no Módulo do PowerShell do Teams.</li>|
| Novembro de 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Correções e melhorias de bugs</li>|
| Novembro de 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Correções e melhorias de bugs</li>|
| Março de 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa o MSAL para autenticação & autorização</li><li>Cmdlets do Pacote de Política Refactored e adiciona atribuição de pacote de grupo</li><li>Aprimoramentos significativos de desempenho para Get-Team cmdlet</li> <li>Opção de registro em log e depuração aprimorado para cmdlets existentes </li> <li>Cmdlets de gerenciamento de modelos adicionados</li> <li>Deprecation of New-CsOnlineSession</li>|
| Fevereiro de 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlets de gerenciamento de modelos adicionados</li><li>Aprimoramentos de mezzo e lote para Get-Team cmdlet</li> <li>Opção de registro em log e depuração aprimorado para cmdlets existentes </li> <li>Cmdlets do Pacote de Política Refactored</li>|
| Dezembro de 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Atualizações para cmdlet new-team com recuperações e duração de sono aumentadas</li>|
| Dezembro de 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Atualizações para Integração do Skype for Business Online</li><li>Correção para o prompt duplicado com Connect-Microsoft Teams</li>|
| Novembro de 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Adiciona cmdlets de pacote de política personalizada</li><li>Correções para os comandos de carregamento de hierarquia de direcionamento</li>|
| Novembro de 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa o MSAL para autenticação & autorização</li><li>Cmdlets do Pacote de Política Refactored e adiciona atribuição de pacote de grupo</li><li>Comandos de carregamento de hierarquia de direcionamento refatorados para usar um modelo assíncrono</li> <li>O usuário será solicitado duas vezes durante a autenticação inicial quando não usar o parâmetro -credential. Os usuários podem passar credenciais usando o parâmetro -credential para evitar um prompt duplicado. Esse comportamento será corrigido na próxima versão.</li> |
| Setembro de 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integração do Skype for Business Online Connector</li> |
| Setembro de 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integração do Skype for Business Online Connector</li> |
| Julho de 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Adicionados [cmdlets](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group) de atribuição de política de grupo</li> |
| Junho de 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integração do Skype for Business Online Connector<li>Get-Team otimizações<li>Confiabilidade aprimorada</li> |
| Junho de 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Pré-carregamento de Cmdlet adicionado<li>Otimizações do .Net Framework</li>   |
| Abril de 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Autenticação e assinatura de assembly<li>Adicionado Get-CsPolicyPackage<li>Adicionado Get-CsUserPolicyPackage<li>Adicionado Get-CsUserPolicyPackageRecommendation<li>Adicionado Grant-CsUserPolicyPackage<li>Adicionado New-CsBatchPolicyPackageAssignmentOperation<li>Adicionado Set-TeamArchivedState<li>Adicionado Set-TeamPicture<li>Removido Get-TeamHelp</li>  |
| Março de 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Adicionado New-CsBatchPolicyAssignmentOperation</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team otimizações</li>  |

### <a name="cmdlet-availability"></a>Disponibilidade de cmdlet

> [!NOTE]
> A lista na tabela abaixo inclui apenas cmdlets que fazem parte nativamente do módulo do Teams PowerShell. Os cmdlets do Teams no módulo S[kype for Business Online Connector](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) não são exibidos. No entanto, à medida que esses cmdlets são migrados de forma nativa para o Teams PowerShell, vamos adicioná-los a esta tabela.

| Cmdlet | Disponível em Visualização Pública | Disponível em GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sim | **Não** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Sim | Sim |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sim | **Não**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sim | Sim |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sim | Sim |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sim | Sim |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | Sim | **Não** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | Sim | Sim |
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
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Sim | Sim |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Sim | Sim |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Sim | Sim |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Sim | Sim |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession?view=skype-ps) | Sim | Sim |
| [New-Team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Sim | Sim |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps) | Sim | Sim |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Sim | Sim |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Sim | Sim |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Sim | Sim |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Sim | Sim |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Sim | **Não** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Sim | Sim |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Sim | **Não** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#remove-your-hierarchy) | Sim | **Não**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Sim | Sim |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Sim | **Não** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Sim | Sim |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Sim | Sim |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Sim | Sim |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Sim | Sim |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamsapp?view=teams-ps) | Sim | Sim |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#apply-your-hierarchy) | Sim | **Não** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamsappinstallation?view=teams-ps) | Sim | **Não** |

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Instalando o PowerShell do Teams](teams-powershell-install.md)

[Gerenciando o Teams com o Teams PowerShell](teams-powershell-managing-teams.md)

[Referência de cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
