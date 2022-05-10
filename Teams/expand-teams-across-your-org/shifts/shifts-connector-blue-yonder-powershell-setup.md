---
title: Usar o PowerShell para conectar turnos ao Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o PowerShell para integrar o Shifts ao Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad0f7e84dcd65f844e457d4821717ff7593593ce
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976010"
---
# <a name="use-powershell-to-connect-shifts-to-blue-yonder-workforce-management"></a>Usar o PowerShell para conectar turnos ao Blue Yonder Workforce Management

## <a name="overview"></a>Visão Geral

Use o [Microsoft Teams Shifts do Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) para integrar o aplicativo Shifts no Microsoft Teams com o Blue Yonder Workforce Management (Blue Yonder WFM). Depois que uma conexão é configurada, os trabalhadores da linha de frente podem exibir e gerenciar diretamente suas agendas no WFM do Remetente Azul de dentro do Shifts.

Neste artigo, explicamos como usar o PowerShell para configurar e configurar o conector para integrar o Shifts ao Blue Yonder WFM.

Para configurar a conexão, execute um script do PowerShell. O script configura o conector, aplica as configurações de sincronização, cria a conexão e mapeia sites WFM blue yonder para equipes. As configurações de sincronização determinam os recursos habilitados no Shifts e as informações de agenda que são sincronizadas entre o WFM do Remetente Azul e o Shifts. Os mapeamentos definem a relação de sincronização entre seus sites do WFM do Remetente Azul e as equipes Teams. Você pode mapear para equipes existentes e novas equipes.

Fornecemos dois scripts. Você pode usar o script, dependendo se deseja mapear para equipes existentes ou criar novas equipes para as quais mapear.

Você pode configurar várias conexões, cada uma com configurações de sincronização diferentes. Por exemplo, se sua organização tiver vários locais com requisitos de agendamento diferentes, crie uma conexão com configurações de sincronização exclusivas para cada local. Tenha em mente que um site WFM do Remetente Azul só pode ser mapeado para uma equipe em um determinado momento. Se um site já estiver mapeado para uma equipe, ele não poderá ser mapeado para outra equipe.

Com o Blue Yonder WFM como o sistema de registro, seus trabalhadores de linha de frente podem ver e trocar turnos, gerenciar sua disponibilidade e solicitar folga em turnos em seus dispositivos. Os gerentes de linha de frente podem continuar a usar o WFM do Blue Yonder para configurar agendamentos.

> [!NOTE]
> Você também pode usar o [assistente do conector shifts](shifts-connector-wizard.md) no Centro de administração do Microsoft 365 para conectar o Shifts ao WFM do Remetente Azul.

## <a name="before-you-begin"></a>Antes de você começar

### <a name="prerequisites"></a>Pré-requisitos

[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

### <a name="admin-role-to-manage-the-connector-using-powershell"></a>Função de administrador para gerenciar o conector usando o PowerShell

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configurar ambiente

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="connect-to-teams"></a>Conexão para Teams

Execute o seguinte para se conectar ao Teams.

```powershell
Connect-MicrosoftTeams
```

Quando for solicitado, entre usando suas credenciais de administrador. Agora você está configurado para executar os scripts neste artigo e os cmdlets do conector do Shifts.

## <a name="identify-the-teams-you-want-to-map"></a>Identificar as equipes que você deseja mapear

> [!NOTE]
> Conclua esta etapa se você estiver mapeando sites WFM do Blue Yonder para equipes existentes. Se você estiver criando novas equipes para as qual mapear, poderá ignorar esta etapa.

No portal do Azure, acesse a página Todos os grupos para [](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) obter uma lista das TeamIds das equipes em sua organização.

Anote as TeamIds das equipes que você deseja mapear. O script solicitará que você insira essas informações.

> [!NOTE]
> Se uma ou mais equipes tiverem um agendamento existente, o script removerá as agendas dessas equipes. Caso contrário, você verá turnos duplicados.

## <a name="run-the-script"></a>Execute o script

Execute o script:

- Para configurar uma conexão e criar novas equipes para mapear, [execute esse script](#set-up-a-connection-and-create-new-teams-to-map).
- Para configurar uma conexão e mapear para equipes existentes, [execute esse script](#set-up-a-connection-and-map-to-existing-teams).

O script executa as ações a seguir. Você será solicitado a inserir detalhes de configuração e configuração.

1. Testa e verifica a conexão com o WFM do Blue Yonder usando as credenciais da conta de serviço WFM do Yonder Azul e as URLs de serviço inseridas.
1. Configura o conector do Shifts.
1. Aplica configurações de sincronização. Essas configurações incluem a frequência de sincronização (em minutos) e os dados de agendamento sincronizados entre o Blue Yonder WFM e o Shifts. Os dados de agendamento são definidos nos seguintes parâmetros:

    - O **parâmetro enabledConnectorScenarios** define os dados que são sincronizados do WFM do Remetente Azul para Shifts. As opções `Shift`são , `UserShiftPreferences``SwapRequest`, , `OpenShift`, `OpenShiftRequest`, `TimeOffRequest``TimeOff`.
    - O **parâmetro enabledWfiScenarios** define os dados sincronizados de Shifts para Blue Yonder WFM. As opções `SwapRequest`são , `OpenShiftRequest`, `TimeOffRequest`. `UserShiftPreferences`

    Para saber mais, confira [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps). Para ver a lista de opções de sincronização com suporte para cada parâmetro, execute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

    > [!IMPORTANT]
    > O script habilita a sincronização para todas essas opções. Se você quiser alterar as configurações de sincronização, poderá fazer isso depois que a conexão for configurada. Para saber mais, confira [Usar o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

1. Cria a conexão.
1. Mapas WFM azul yonder para equipes. Os mapeamentos são baseados nas IDs de site do WFM do Remetente Azul e nas TeamIds que você insere ou novas equipes criadas, dependendo do script executado. Se uma equipe tiver um agendamento existente, o script removerá os dados de agendamento para o intervalo de data e hora especificado.

Uma mensagem de êxito na tela indica que a conexão foi configurada com êxito.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Se você precisar fazer alterações em uma conexão

Para fazer alterações em uma conexão após a configuração, consulte Usar o PowerShell para gerenciar sua conexão [shifts com o Blue Yonder Workforce Management](shifts-connector-powershell-manage.md). Por exemplo, você pode atualizar configurações de sincronização, mapeamentos de equipe e desabilitar a sincronização para uma conexão.

## <a name="scripts"></a>Scripts

### <a name="set-up-a-connection-and-create-new-teams-to-map"></a>Configurar uma conexão e criar novas equipes para mapear

```powershell
#Map WFM sites to teams script
Write-Host "Map WFM sites to teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency"

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail $AdminEmailList
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

#Create a new Teams team with owner set to system account and name set to the site name
Write-Host "Creating a Teams team"
$teamsTeamName = Read-Host -Prompt "Input the Teams team name"
$Team = New-Team -DisplayName $teamsTeamName -Visibility "Public" -Owner $teamsUserId
Write-Host "Success"
$TeamsTeamId=$Team.GroupId

#add users to the Team for Shifts
Write-Host "Adding users to Teams team"
$currentUser = Read-Host -Prompt "Input the current user's user name or ID"
Add-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
$failedWfmUsers=@()
foreach ($user in $WFMUsers) {
    try {
    $userEmail = $user.Name + "@" +$domain
    Add-TeamUser -GroupId $TeamsTeamId -User $userEmail
    } catch {
        $failedWfmUsers+=$user
    }
}
if($failedWfmUsers.Count -gt 0){
    Write-Host "There are WFM users not existed in Teams tenant:"
    write $failedWfmUsers
}

#Enable scheduling in the group
$RequestBody = @{
    Enabled = $true
    TimeZone = "America/Los_Angeles"
}
$teamUpdateUrl="https://graph.microsoft.com/v1.0/teams/"+$TeamsTeamId+"/schedule"
$Schedule = Invoke-MgGraphRequest -Uri $teamUpdateUrl -Method PUT -Body $RequestBody

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the new team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"

$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}

#The Teams admin was set as an owner directly when creating a new team, removing it from owners
Remove-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
Disconnect-MgGraph
```

### <a name="set-up-a-connection-and-map-to-existing-teams"></a>Configurar uma conexão e mapear para equipes existentes

```powershell
#Map WFM sites to existing teams script
Write-Host "Map WFM sites to existing teams"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview) 
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365 user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency in minutes. Value should be equal to or more than 10."

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail AdminEmailList

$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

$TeamsTeamId = Read-Host -Prompt "Input the ID of the Teams team to be mapped"
#Clear schedule of the Teams team
Write-Host "Clear schedule of the existing team"
$startTime = Read-Host -Prompt "Input the start time of clear schedule"
$endTime = Read-Host -Prompt "Input the end time of clear schedule"

$entityTypeString = Read-Host -Prompt 'Input the entity types of clear schedule'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$entityType = $entityTypeString -Split {$Delimiters -contains $_}
$entityType = $entityType.Trim()
$entityType = $entityType.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
Remove-CsTeamsShiftsScheduleRecord -TeamId $TeamsTeamId -DateRangeStartDate $startTime -DateRangeEndDate $endTime -ClearSchedulingGroup:$True -EntityType $entityType -DesignatedActorId $$teamsUserId

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the existing team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"


$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Disconnect-MgGraph
```

## <a name="shifts-connector-cmdlets"></a>Cmdlets do conector shifts

Para obter ajuda com cmdlets do conector shifts, incluindo os cmdlets usados nos scripts, **pesquise CsTeamsShiftsConnection** na referência de [cmdlet Teams PowerShell](/powershell/teams/intro?view=teams-ps). Aqui estão links para alguns cmdlets comumente usados.

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
- [Usar o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)
- [Teams de cmdlet do PowerShell](/powershell/teams/intro?view=teams-ps)