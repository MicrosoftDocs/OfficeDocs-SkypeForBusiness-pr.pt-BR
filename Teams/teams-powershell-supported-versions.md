---
title: Teams módulo do PowerShell – Versões com suporte
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba mais sobre as versões com suporte Teams módulo do PowerShell, usadas para administração de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 242c7c43b2af31b11e4183fdf3b9ed1b00f4bb1b
ms.sourcegitcommit: 204e4654f2c3977db260670f3ee1784d1ad6ed17
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2022
ms.locfileid: "64866236"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams módulo do PowerShell – Versões com suporte

Microsoft Teams versões do Módulo do PowerShell (TPM) na série 4.x.x ou posterior serão as únicas versões com suporte no futuro. Todas as versões anteriores estão no caminho de desativação. É recomendável atualizar o módulo Teams PowerShell para a versão mais recente.



## <a name="new-organizations"></a>Novas organizações

As organizações recém-integradas ao Teams só poderão usar o Módulo do PowerShell do Teams na série 4.x.x ou posterior a partir de 1º de abril de 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizações atuais (não Ativas no TPM)

As organizações que não usaram o Módulo do PowerShell do Teams nos últimos três meses (22 de janeiro – 22 de março de 22) só poderão usar o Módulo do PowerShell do Teams na série 4.x.x ou posterior a partir de 1º de abril de 2022.



## <a name="current-organizations-tpm-active"></a>Organizações atuais (TPM ativo)

As organizações que usam o Módulo do PowerShell do Teams nos últimos três meses (22 de janeiro – 22 de março de 2022) só poderão usar o Módulo do PowerShell do Teams na série 4.x.x ou posterior a partir de 15 de junho de 2022. Postagem do centro de mensagens para referência – MC350371. 



## <a name="important-notes"></a>Observações importantes

- As notas de versão para todas as Teams do Módulo do PowerShell podem ser encontradas Teams de versão [do PowerShell](teams-powershell-release-notes.md).

- Para atualizar qualquer módulo do PowerShell, você deve usar o mesmo método usado para instalar o módulo. Por exemplo, se você usou o Install-Module originalmente, deverá usar [Update-Module](/powershell/module/powershellget/update-module) para obter a versão mais recente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Se estiver atualizando do Teams PowerShell versão 1.1.6, atualize seus scripts para usar `Connect-MicrosoftTeams` em vez de `New-CsOnlineSession`.

-   Durante a atualização, é recomendável não usar o TPM 4.x.x/3.x.x junto com versões anteriores à 3.0.0. Por exemplo, não é recomendável usar as versões 4.x.x & 2.6.0 juntas para diferentes operações de administrador na mesma organização. 

- Alterações relacionadas
  * Atualizações do Get-CsOnlineUser & Get-CsOnlineVoiceUser no TPM 3.x.x e posteriores – mais detalhes em [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (postagem do Centro de mensagens – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Alterações chegando Telefone atribuição de número – mais detalhes em [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Postagem do Centro de mensagens – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)

-   Ao usar o TPM 4.x.x ou posterior, é recomendável não usar nenhum dos cmdlets preteridos ou sem suporte mencionados [abaixo](#deprecated-cmdlets). 



## <a name="deprecated-cmdlets"></a>Cmdlets preteridos

- Alguns dos cmdlets que foram preteridos recentemente estão listados abaixo. Detalhes sobre o mesmo podem ser encontrados nas respectivas documentações públicas. 
  * [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  * [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  * [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  * [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
  * [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  
  * [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  * [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)


- Os cmdlets que não têm suporte/são relevantes para Microsoft Teams cenários estão listados abaixo. 
  * [Obter| Set]-CsUserPstnSettings
  * [Obter| Definir| Habilitar| Disable]-CsMeetingRoom
  * [Conceder| Obter| Definir| Novo| Remove]-CsConferencingPolicy
  * [Conceder| Obter| Definir| Novo| Remove]-CsClientPolicy
  * [Conceder| Get]-CsHostedVoicemailPolicy
  * [Conceder| Obter| Definir| Novo| Remove]-CsMobilityPolicy
  * [Conceder| Get] CsVoiceRoutingPolicy
  * [Conceder| Get]-CsBroadcastMeetingPolicy
  * [Conceder| Get]-CsCloudMeetingPolicy
  * [Conceder| Get]-CsGraphPolicy
  * [Conceder| Obter| Definir| Novo| Remove]-CsExternalUserCommunicationPolicy
  * [Conceder| Obter| Set]-CsIPPhonePolicy
  * Get-CsUserServicesPolicy
  * [Obter| Set]-CsBroadcastMeetingConfiguration
  * [Obter| Set]-CsOAuthConfiguration
  * [Obter| Set]-CsMeetingConfiguration
  * [Obter| Set]-CsTenantHybridConfiguration
  * [Obter| Set]-CsPushNotificationConfiguration
  * [Obter| Set]-CsUCPhoneConfiguration
  * Get-CsImFilterConfiguration
  * Get-CsAudioConferencingProvider
  * [Obter| Set]-CsTenantPublicProvider
  * Get-CsHostingProvider
  * [Obter| Definir| Registrar| Unregister]-CsHybridPSTNAppliance
  * [Obter| Definir| Novo| Remove]-CsHybridPSTNSite
  * [Obter| Set]- CsHybridMediationServer
  * [Obter| Definir| Novo| Remove]-CsTenantUpdateTimeWindow
  * Get-CsUserLocationStatus
  * Invoke-CsUcsRollback
  * [Obter| Definir| Novo| Remove]-CsTeamsPinnedApp
  * [Obter| Definir| Novo| Remove]-CsTenantCatalogApp
  * [Obter| Definir| Novo| Remove]-CsGlobalCatalogApp
  * [Obter| Definir| Novo| Remove]-CsDefaultCatalogApp
  * [Obter| Definir| Novo| Remove]-CsTeamsAppPreset



## <a name="related-topics"></a>Tópicos relacionados

[Teams de versão do PowerShell](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Gerenciar Teams com Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams de cmdlet](/powershell/module/teams) 

[Skype for Business de cmdlet](/powershell/module/skype) 
