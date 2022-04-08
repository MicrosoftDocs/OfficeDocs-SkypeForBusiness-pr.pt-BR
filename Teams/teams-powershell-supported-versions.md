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
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712955"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams módulo do PowerShell – Versões com suporte

Microsoft Teams versões do Módulo do PowerShell (TPM) na série 4.x.x ou superior serão as únicas versões com suporte no futuro. Todas as versões anteriores estão no caminho de desativação. É recomendável atualizar o módulo Teams PowerShell para a versão mais recente.



## <a name="new-organizations"></a>Novas organizações

As organizações recém-integradas ao Teams só poderão usar o Módulo do PowerShell do Teams na série 4.x.x ou superior a partir de 1º de abril de 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizações atuais (não Ativas no TPM)

As organizações que não usaram o Módulo do PowerShell do Teams nos últimos três meses (22 de janeiro – 22 de março de 2022) só poderão usar o Módulo do PowerShell do Teams na série 4.x.x ou posterior a partir de 1º de abril de 2022.



## <a name="current-organizations-tpm-active"></a>Organizações atuais (TPM ativo)

As organizações que usam o Módulo do PowerShell do Teams nos últimos três meses (22 de janeiro – 22 de março de 22) só poderão usar o Módulo do PowerShell do Teams na série 4.x.x ou posterior a partir de 15 de junho de 2022. Postagem do centro de mensagens para referência – MC350371. 



## <a name="important-notes"></a>Observações importantes

- As notas de versão para todas as Teams do Módulo do PowerShell podem ser encontradas Teams de versão [do PowerShell](teams-powershell-release-notes.md).

- Para atualizar qualquer módulo do PowerShell, você deve usar o mesmo método usado para instalar o módulo. Por exemplo, se você usou o Install-Module originalmente, deverá usar [Update-Module](/powershell/module/powershellget/update-module) para obter a versão mais recente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Se estiver atualizando do Teams PowerShell versão 1.1.6, atualize seus scripts para usar `Connect-MicrosoftTeams` em vez de `New-CsOnlineSession`.

-   Durante a atualização, é recomendável não usar o TPM 4.x.x/3.x.x junto com versões anteriores à 3.0.0. Por exemplo, não é recomendável usar as versões 4.x.x & 2.6.0 juntas para diferentes operações de administrador na mesma organização. 

- Alterações relacionadas
  * Atualizações para Get-CsOnlineUser & Get-CsOnlineVoiceUser no TPM 3.x.x e superior – mais detalhes em [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (postagem do Centro de mensagens – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Alterações chegando Telefone atribuição de número – mais detalhes em [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Postagem do Centro de mensagens – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>Cmdlets preteridos

Alguns dos cmdlets que foram preteridos recentemente ou não têm suporte para cenários Microsoft Teams são listados abaixo. Detalhes sobre o mesmo podem ser encontrados nas respectivas documentações públicas. 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings), [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom), [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom), [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom), [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>Tópicos relacionados

[Teams de versão do PowerShell](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Gerenciar Teams com Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams de cmdlet](/powershell/module/teams) 

[Skype for Business de cmdlet](/powershell/module/skype) 
