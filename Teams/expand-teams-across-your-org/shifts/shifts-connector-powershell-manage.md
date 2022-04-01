---
title: Use o PowerShell para gerenciar sua conexão shifts com o Gerenciamento de Força de Trabalho de Blue Yonder
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o PowerShell para gerenciar sua conexão shifts com o Gerenciamento de Força de Trabalho do Blue Yonder.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593627"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Use o PowerShell para gerenciar sua conexão shifts com o Gerenciamento de Força de Trabalho de Blue Yonder

## <a name="overview"></a>Visão geral

O [Microsoft Teams conector shifts para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) permite integrar o aplicativo Shifts no Microsoft Teams com o Blue Yonder Workforce Management (Blue Yonder WFM). Depois de configurar uma conexão, seus funcionários de linha de frente podem exibir e gerenciar seus agendamentos no WFM do Blue Yonder de dentro de Shifts.

Você pode usar o [assistente do conector shifts](shifts-connector-wizard.md) no Centro de administração do Microsoft 365 ou [no PowerShell](shifts-connector-blue-yonder-powershell-setup.md) para configurar uma conexão. Depois que uma conexão é configurada, você a gerencia usando [cmdlets do PowerShell do conector shifts](#shifts-connector-cmdlets).

Este artigo descreve como usar o PowerShell para fazer o seguinte:

- [Verificar o status da configuração de conexão](#check-connection-setup-status)
- [Exibir um relatório de erro para uma conexão](#view-an-error-report-for-a-connection)
- [Resolver erros de conexão](#resolve-connection-errors)
- [Alterar configurações de conexão](#change-connection-settings)
- [Desmap uma equipe de uma conexão e mapeá-la para outra conexão](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Desabilitar a sincronização para uma conexão](#disable-sync-for-a-connection)

> [!NOTE]
> Este artigo supõe que você já tenha definido uma conexão com o WFM do Blue Yonder, usando o assistente ou o PowerShell.

## <a name="before-you-begin"></a>Antes de você começar

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configurar ambiente

> [!NOTE]
> Siga estas etapas para configurar seu ambiente antes de executar qualquer um dos comandos ou scripts neste artigo.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>Verificar o status da configuração de conexão
<a name="setup_status"> </a>

Para verificar o status da conexão configurada usando a ID da operação recebida no email:

1. [Configurar seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso).
1. Execute o seguinte comando. Este comando fornece o status geral dos mapeamentos de equipe para a conexão.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Para saber mais, confira [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps).

## <a name="view-an-error-report-for-a-connection"></a>Exibir um relatório de erro para uma conexão
<a name="error_report"> </a>

Você pode executar um relatório que mostra detalhes de erro para uma conexão. O relatório lista mapeamentos de equipe e usuário que tiveram êxito e falharam. Ele também fornece informações sobre quaisquer problemas relacionados às contas associadas à conexão.

1. [Configurar seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso).
1. Obter uma lista de relatórios de erros para uma conexão.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Para exibir um relatório de erro específico, execute o seguinte comando:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Para saber mais, confira [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps).

## <a name="resolve-connection-errors"></a>Resolver erros de conexão

### <a name="user-mapping-errors"></a>Erros de mapeamento do usuário

Erros de mapeamento de usuário podem ocorrer se um ou mais usuários em um site WFM do Blue Yonder não for membro da equipe mapeada no Teams. Para resolver esse problema, certifique-se de que os usuários da equipe mapeada corresponderão aos usuários no site WFM do Blue Yonder.

Para exibir detalhes de usuários não mapeados, [configurar](#set-up-your-environment) seu ambiente (caso ainda não tenha feito) e execute o script a seguir.

```powershell
#View sync errors script 
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x 
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Erros de autorização de conta

Erros de autorização de conta podem ocorrer se a conta de serviço WFM blue yonder ou Microsoft 365 de conta do sistema estão incorretas ou não têm as permissões necessárias.

Para alterar sua conta de serviço WFM blue yonder ou credenciais de conta do sistema Microsoft 365 para a conexão, você pode executar o cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) ou usar o script do PowerShell na seção [Alterar](#change-connection-settings) configurações de conexão deste artigo.

## <a name="change-connection-settings"></a>Alterar configurações de conexão
<a name="change_settings"> </a>

Use este script para alterar as configurações de conexão. Configurações que você pode alterar incluem sua conta de serviço WFM e senha do Blue Yonder, Microsoft 365 conta do sistema, mapeamentos de equipe e configurações de sincronização.

As configurações de sincronização incluem a frequência de sincronização (em minutos) e os dados de agendamento sincronizados entre o WFM do Blue Yonder e Shifts. Os dados de agendamento são definidos nos seguintes parâmetros, que você pode exibir executando [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

- O **parâmetro enabledConnectorScenarios** define dados que são sincronizados do WFM do Blue Yonder para Shifts. As opções são `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
- O **parâmetro enabledWfiScenarios** define dados que são sincronizados de Shifts para Blue Yonder WFM. As opções são `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Se você optar por não sincronizar turnos abertos, solicitações de turno aberto, solicitações de troca ou solicitações de tempo de folga entre Shifts e WFM do Blue Yonder, há outra etapa que você precisa fazer para ocultar o recurso em Shifts. Depois de executar esse script, siga as etapas na seção Desabilitar turnos abertos, abrir solicitações de [turnos,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) solicitações de troca e solicitações de folga posteriormente neste artigo.

> [!IMPORTANT]
> Para configurações que você não deseja alterar, você precisará inserir as configurações originais quando for solicitado pelo script.

[Configurar seu ambiente](#set-up-your-environment) (caso ainda não tenha feito) e execute o script a seguir.

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview) 
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping 
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping 
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Desabilitar turnos abertos, solicitações de turnos abertos, solicitações de troca e solicitações de folga

> [!IMPORTANT]
> Siga estas etapas somente se você optar por desabilitar turnos abertos, solicitações de turno aberto, solicitações de troca ou solicitações de tempo [](#change-connection-settings) de folga usando o script na seção Alterar configurações de conexão anteriormente neste artigo ou usando o cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps). Concluir esta etapa oculta a funcionalidade em Shifts. Sem essa segunda etapa, os usuários ainda verão o recurso em Shifts e receberão uma mensagem de erro "operação sem suporte" se tentarem usá-lo.

Para ocultar os turnos abertos, solicitações de troca e solicitações de folga no Shifts, use o tipo [](/graph/api/resources/schedule?view=graph-rest-1.0) de recurso agendar API do Graph para definir os seguintes parâmetros ```false``` para cada equipe mapeada para um site WFM do Blue Yonder:

- Turnos abertos: ```openShiftsEnabled```
- Solicitações de troca:  ```swapShiftsRequestsEnabled```
- Solicitações de tempo de folga: ```timeOffRequestsEnabled```

Para ocultar solicitações de turnos abertos em Turnos,  vá para Configurações turnos e, em seguida, desativar a **configuração Abrir turnos**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Desmap uma equipe de uma conexão e mapeá-la para outra conexão

> [!NOTE]
> A Microsoft 365 do sistema deve ser a mesma para ambas as conexões. Se não for, você obterá uma mensagem de erro "Esse perfil de ator designado não tem privilégios de propriedade de equipe".

Se você quiser desmapear uma equipe de uma conexão e mapeá-la para outra conexão:

1. [Configurar seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso).
1. Exibir uma lista de todos os mapeamentos de equipe para uma conexão.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Remova um mapeamento de equipe da conexão.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Mapeie a equipe para outra conexão.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Para saber mais, confira [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) e [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps).

## <a name="disable-sync-for-a-connection"></a>Desabilitar a sincronização para uma conexão

Use esse script para desabilitar a sincronização de uma conexão. Lembre-se de que esse script não remove ou exclui uma conexão. Ele desliga a sincronização para que nenhum dado seja sincronizado entre Shifts e Blue Yonder WFM para a conexão especificada.

[Configurar seu ambiente](#set-up-your-environment) (caso ainda não tenha feito) e execute o script a seguir.

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Cmdlets do conector de turnos

Para ajudar com cmdlets do conector Shifts, pesquise **CsTeamsShiftsConnection** na referência do [cmdlet Teams PowerShell](/powershell/teams/intro?view=teams-ps). Aqui estão links para alguns cmdlets comumente usados.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>Artigos relacionados

- [Conectores de turnos](shifts-connectors.md)
- [Use o assistente de conector de turnos para conectar Shifts ao Gerenciamento de Força de Trabalho de Zona Azul](shifts-connector-wizard.md)
- [Usar o PowerShell para conectar Turnos ao Gerenciamento de Força de Trabalho do Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)
- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)