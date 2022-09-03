---
title: Módulo do PowerShell do Teams – Versões com suporte
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba mais sobre as versões com suporte do Módulo do PowerShell do Teams, usadas para administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28e16c248957518ca16eb3eff7e082ebe6bd9bd
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590318"
---
# <a name="teams-powershell-module---supported-versions"></a>Módulo do PowerShell do Teams – Versões com suporte

As versões do Microsoft Teams PowerShell Module (TPM) na série 4.x.x ou posterior são as únicas versões com suporte agora. Todas as versões anteriores estão totalmente desativadas em ambientes comerciais desde 15 de junho de 2022 & deixarão de funcionar (postagem do Centro de mensagens para referência – MC350371). 

É recomendável atualizar para a versão mais recente do Módulo do PowerShell do Teams.


## <a name="important-notes"></a>Observações importantes

- As notas sobre a versão de todas as versões do Módulo do PowerShell do Teams podem ser encontradas nas notas [de versão do PowerShell do Teams](teams-powershell-release-notes.md).

- Para atualizar qualquer módulo do PowerShell, você deve usar o mesmo método usado para instalar o módulo. Por exemplo, se você usou o Install-Module originalmente, deverá usar [Update-Module](/powershell/module/powershellget/update-module) para obter a versão mais recente.

  ```powershell
  Update-Module MicrosoftTeams
  ```

- Se estiver atualizando do Módulo do Teams PowerShell versão 1.1.6, atualize seus scripts para usar `Connect-MicrosoftTeams` em vez de `New-CsOnlineSession`.

- Durante a atualização, é recomendável não usar o TPM 4.x.x/3.x.x junto com versões anteriores à 3.0.0. Por exemplo, não é recomendável usar as versões 4.x.x & 2.6.0 juntas para diferentes operações de administrador na mesma organização.

- Alterações relacionadas
  - Atualizações para Get-CsOnlineUser & Get-CsOnlineVoiceUser no TPM 3.x.x e posterior – mais detalhes em [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) (postagem do Centro de mensagens – MC340774).

  - Alterações na atribuição de número de telefone – mais detalhes em [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (postagem do centro de mensagens – MC316139).

  - Alterações de parâmetro Get-CsTenant - mais detalhes em [Get-CsTenant](/powershell/module/skype/get-cstenant) (postagem do Centro de mensagens – MC365397).
  
  - Se os scripts usam cmdlets New/Set of Policy ou Configuration com parâmetros de tipo PSListModifier, é recomendável usar a versão mais recente (4.2.0 ou posterior). Postagem do centro de mensagens para referência – MC397428.

  - [Novo| Os cmdlets Get]-CsCloudCallDataConnection agora têm suporte nas versões 4.6.0 ou posteriores (postagem do Centro de mensagens – MC408993).

- Ao usar o TPM 4.x.x ou posterior, é recomendável não usar nenhum dos cmdlets preteridos ou sem suporte mencionados [abaixo](#deprecated-cmdlets).

## <a name="deprecated-cmdlets"></a>Cmdlets preteridos

- Alguns dos cmdlets que foram preteridos recentemente estão listados abaixo. Detalhes sobre o mesmo podem ser encontrados nas respectivas documentações públicas.
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint), Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- Os cmdlets que não têm suporte/são relevantes para cenários do Microsoft Teams estão listados abaixo.
  - [Obter| Set]-CsUserPstnSettings
  - [Obter| Definir| Habilitar| Disable]-CsMeetingRoom
  - [Conceder| Obter| Definir| Novo| Remove]-CsConferencingPolicy
  - [Conceder| Obter| Definir| Novo| Remove]-CsClientPolicy
  - [Conceder| Get]-CsHostedVoicemailPolicy
  - [Conceder| Obter| Definir| Novo| Remove]-CsMobilityPolicy
  - [Conceder| Get]-CsVoiceRoutingPolicy
  - [Conceder| Get]-CsBroadcastMeetingPolicy
  - [Conceder| Get]-CsCloudMeetingPolicy
  - [Conceder| Get]-CsGraphPolicy
  - [Conceder| Obter| Definir| Novo| Remove]-CsExternalUserCommunicationPolicy
  - [Conceder| Obter| Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Obter| Set]-CsBroadcastMeetingConfiguration
  - [Obter| Set]-CsOAuthConfiguration
  - [Obter| Set]-CsMeetingConfiguration
  - [Obter| Set]-CsTenantHybridConfiguration
  - [Obter| Set]-CsPushNotificationConfiguration
  - [Obter| Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Obter| Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [Obter| Definir| Registrar| Unregister]-CsHybridPSTNAppliance
  - [Obter| Definir| Novo| Remove]-CsHybridPSTNSite
  - [Obter| Set]-CsHybridMediationServer
  - [Obter| Definir| Novo| Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Obter| Definir| Novo| Remove]-CsTeamsPinnedApp
  - [Obter| Definir| Novo| Remove]-CsTenantCatalogApp
  - [Obter| Definir| Novo| Remove]-CsGlobalCatalogApp
  - [Obter| Definir| Novo| Remove]-CsDefaultCatalogApp
  - [Obter| Definir| Novo| Remove]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [Obter| Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>Tópicos relacionados

[Notas de versão do PowerShell do Teams](teams-powershell-release-notes.md)

[Instalar o PowerShell do Microsoft Teams](teams-powershell-install.md)

[Gerenciar o Teams com o Teams PowerShell](teams-powershell-managing-teams.md)

[Referência de cmdlet do Microsoft Teams](/powershell/module/teams)

[Skype for Business de cmdlet](/powershell/module/skype)
