---
title: Microsoft Teams Notas de versão do PowerShell
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
ms.openlocfilehash: f319e95b4b68c7b9a20c8c6fff238f70878e7a32
ms.sourcegitcommit: a628b22c9a0ef3bcd7dee3f308a79b4c427872cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2021
ms.locfileid: "52491798"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams Notas de versão do PowerShell

Esta página fornece o log de alterações Teams versão mais recente do PowerShell para versões de Disponibilidade Geral e Visualização Pública.

## <a name="release-notes"></a>Notas de versão

> [!NOTE]
> **-preview** na coluna versão abaixo representa atualizações para Teams visualização pública do PowerShell.

| Data | Versão | Atualizações |
|------- | -------------------- | ------------------------------ |
| Maio de 2021 | [3.0.0] |<li>Atualizações para o logon accessToken com Connect-MicrosoftTeams - matriz de token unificado em vez de parâmetros de token de acesso específicos do recurso</li><li>Removidas todas as referências do AADGraph como AADGraph está chegando ao fim da vida útil</li>|
| Maio de 2021 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Atualização de . NETCore 2.1 a 3.1</li><li>Cmdlet adicionado para obter região multi-geográfica para usuários e grupos</li><li>Correções para autenticação integrada do Windows usar -AccountId com Connect-MicrosoftTeams</li><li>Os cmdlets TeamsCallHoldPolicy agora estão disponíveis</li><li>Atualizações para parâmetros de entrada e formatos de saída de muitos comandos</li><li>Corrige um grande problema de latência ao remotar comandos</li><li>Recursos de pacote personalizado ga</li>|
| Abril de 2021 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Correções para autenticação Windows integrada para usar -AccountId com Conexão-MicrosoftTeams.</li><li>Adicionado cmdlet para obter detalhes do total de eventos de notificação de alteração que podem ser enviados aos usuários.</li><li>Adicionado cmdlet para obter região multi-geográfica para usuários e grupos.</li><li>A manipulação de valores passados para o nome teamsEnvironment foi sensível a minúsculas. Isso foi corrigido.</li><li>Principal refator do gerenciamento de sessão remota dentro do módulo para facilitar testes de unidade. Não deve haver nenhuma alteração funcional para administradores de locatários.</li>|
| Abril de 2021 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Formatação fixa de cmdlets existentes (por exemplo, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy e muito mais).</li><li>Lista de parâmetros atualizada de cmdlets de gerenciamento de política.</li>|
| Março de 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa o MSAL para autenticação & autorização</li> <li>Connect-MicrosoftTeams é o ponto de entrada para todos os cmdlets.</li><li>New-csOnlineSession não está mais disponível. Ele foi substituído por Conexão-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection não é mais necessário. O recurso foi implementado de forma nativa no Teams PowerShell.</li> <li>Cmdlets do Pacote de Política Refactored e adiciona atribuição de pacote de grupo</li><li>Aprimoramentos significativos de desempenho para Get-Team cmdlet</li> <li>Opção de registro em log e depuração aprimorado para cmdlets existentes </li> <li>Cmdlets de gerenciamento de modelos adicionados</li> <li>Deprecation of New-CsOnlineSession</li>|
| Fevereiro de 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlets de gerenciamento de modelos adicionados</li><li>Aprimoramentos de mezzo e lote para Get-Team cmdlet</li> <li>Opção de registro em log e depuração aprimorado para cmdlets existentes </li> <li>Cmdlets do Pacote de Política Refactored</li>|
| Dezembro de 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Atualizações para cmdlet new-team com recuperações e duração de sono aumentadas</li>|
| Dezembro de 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Atualizações para a integração Skype for Business Online</li><li>Correção do prompt duplicado com Connect-Microsoft Teams</li>|
| Novembro de 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Adiciona cmdlets de pacote de política personalizada</li><li>Correções para os comandos de carregamento de hierarquia de direcionamento</li>|
| Novembro de 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa o MSAL para autenticação & autorização</li><li>Cmdlets do Pacote de Política Refactored e adiciona atribuição de pacote de grupo</li><li>Comandos de carregamento de hierarquia de direcionamento refatorados para usar um modelo assíncrono</li> <li>O usuário será solicitado duas vezes durante a autenticação inicial quando não usar o parâmetro -credential. Os usuários podem passar credenciais usando o parâmetro -credential para evitar um prompt duplicado. Esse comportamento será corrigido na próxima versão.</li> |
| Setembro de 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Integração do Conector Online</li> |
| Setembro de 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Integração do Conector Online</li> |
| Julho de 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Adicionados [cmdlets](./assign-policies.md#assign-a-policy-to-a-group) de atribuição de política de grupo</li> |
| Junho de 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Integração do Conector Online<li>Get-Team otimizações<li>Confiabilidade aprimorada</li> |
| Junho de 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Pré-carregamento de Cmdlet adicionado<li>Otimizações do .Net Framework</li>   |
| Abril de 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Autenticação e assinatura de assembly<li>Adicionado Get-CsPolicyPackage<li>Adicionado Get-CsUserPolicyPackage<li>Adicionado Get-CsUserPolicyPackageRecommendation<li>Adicionado Grant-CsUserPolicyPackage<li>Adicionado New-CsBatchPolicyPackageAssignmentOperation<li>Adicionado Set-TeamArchivedState<li>Adicionado Set-TeamPicture<li>Removido Get-TeamHelp</li>  |
| Março de 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Adicionado New-CsBatchPolicyAssignmentOperation</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team otimizações</li>  |

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)

[Instalando Teams PowerShell](teams-powershell-install.md)

[Gerenciando Teams com Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams de cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business de cmdlet](/powershell/skype/intro?view=skype-ps)
