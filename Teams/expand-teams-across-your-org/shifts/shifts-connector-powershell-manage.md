---
title: Use o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4edf815a3ce21a820fa292a06d41275c97d78a5
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647818"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Use o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management

## <a name="overview"></a>Visão Geral

O [conector do Microsoft Teams Shifts para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) permite que você integre o aplicativo Shifts no Microsoft Teams ao Blue Yonder Workforce Management (Blue Yonder WFM). Depois de configurar uma conexão, os funcionários da linha de frente podem exibir e gerenciar diretamente suas agendas no Blue Yonder WFM de dentro do Shifts.

Você pode usar o [assistente do conector shifts](shifts-connector-wizard.md) no Centro de administração do Microsoft 365 ou [no PowerShell](shifts-connector-blue-yonder-powershell-setup.md) para configurar uma conexão. Depois que uma conexão for configurada, você a gerenciará usando [cmdlets do PowerShell do conector shifts](#shifts-connector-cmdlets).

Este artigo descreve como usar o PowerShell para fazer o seguinte:

- [Verificar o status da configuração da conexão](#check-connection-setup-status)
- [Exibir um relatório de erros para uma conexão](#view-an-error-report-for-a-connection)
- [Resolver erros de conexão](#resolve-connection-errors)
- [Alterar as configurações de conexão](#change-connection-settings)
- [Desmapear uma equipe de uma conexão e mapeá-la para outra conexão](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Desabilitar a sincronização para uma conexão](#disable-sync-for-a-connection)

> [!NOTE]
> Este artigo pressupõe que você já configurou uma conexão com o Blue Yonder WFM, usando o assistente ou o PowerShell.

## <a name="before-you-begin"></a>Antes de você começar

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configurar ambiente

> [!NOTE]
> Siga estas etapas para configurar seu ambiente antes de executar qualquer um dos comandos ou scripts neste artigo.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. Conecte-se ao Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Quando for solicitado, entre usando suas credenciais de administrador. Agora você está configurado para executar os scripts neste artigo e os cmdlets do conector do Shifts.

## <a name="check-connection-setup-status"></a>Verificar o status da configuração da conexão

<a name="setup_status"> </a>

Para verificar o status da conexão configurada usando a ID da operação recebida no email:

1. [Configure seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso).
1. Execute o comando a seguir. Esse comando fornece o status geral dos mapeamentos de equipe para a conexão.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Para saber mais, confira [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).

## <a name="view-an-error-report-for-a-connection"></a>Exibir um relatório de erros para uma conexão

<a name="error_report"> </a>

Você pode executar um relatório que mostra detalhes de erro para uma conexão. O relatório lista mapeamentos de equipe e usuário que tiveram êxito e falharam. Ele também fornece informações sobre quaisquer problemas relacionados às contas associadas à conexão.

1. [Configure seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso).
1. Obtenha uma lista de relatórios de erros para uma conexão.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Para exibir um relatório de erros específico, execute o seguinte comando:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Para saber mais, confira [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).

## <a name="resolve-connection-errors"></a>Resolver erros de conexão

### <a name="user-mapping-errors"></a>Erros de mapeamento de usuário

Erros de mapeamento de usuário poderão ocorrer se um ou mais usuários em uma instância do Blue Yonder WFM não for membro da equipe mapeada no Teams. Para resolver esse problema, verifique se os usuários na equipe mapeada correspondem aos usuários na instância de WFM Azul.

Para exibir detalhes de usuários não mapeados [, configure](#set-up-your-environment) seu ambiente (caso ainda não tenha feito isso) e execute o script a seguir.

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

Erros de autorização de conta podem ocorrer se a conta de serviço blue yonder WFM ou as credenciais da conta do sistema do Microsoft 365 estão incorretas ou não têm as permissões necessárias.

Para alterar sua conta de serviço do Blue Yonder WFM ou as credenciais da conta de sistema do Microsoft 365 para a conexão, você pode executar o cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) ou usar o script do PowerShell [](#change-connection-settings) na seção Alterar configurações de conexão deste artigo.

## <a name="change-connection-settings"></a>Alterar as configurações de conexão
<a name="change_settings"> </a>

Use esse script para alterar as configurações de conexão. As configurações que você pode alterar incluem sua conta de serviço e senha do Blue Yonder WFM, conta de sistema do Microsoft 365, mapeamentos de equipe e configurações de sincronização.

As configurações de sincronização incluem a frequência de sincronização (em minutos) e os dados de agendamento sincronizados entre o Blue Yonder WFM Shifts. Os dados de agendamento são definidos nos parâmetros a seguir, que você pode exibir executando [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector).

- O **parâmetro enabledConnectorScenarios** define os dados sincronizados do Blue Yonder WFM shifts. As opções `Shift`são , `UserShiftPreferences``SwapRequest`, , `OpenShift`, `OpenShiftRequest`, `TimeOffRequest``TimeOff`.
- O **parâmetro enabledWfiScenarios** define os dados sincronizados de Shifts para Blue Yonder WFM. As opções `SwapRequest`são , `OpenShiftRequest`, `TimeOffRequest`. `UserShiftPreferences`

    > [!NOTE]
    > Se você optar por não sincronizar turnos abertos, abrir solicitações de turno, solicitações de permuta ou solicitações de folga entre Shifts e Blue Yonder WFM, há outra etapa que você precisa fazer para ocultar a funcionalidade no Shifts. Depois de executar esse script, siga as etapas na seção Desabilitar turnos abertos, abrir solicitações de [turnos,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) solicitações de permuta e solicitações de folga posteriormente neste artigo.

> [!IMPORTANT]
> Para as configurações que você não deseja alterar, você precisará inserir novamente as configurações originais quando for solicitado pelo script.

[Configure seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso) e execute o script a seguir.

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Desabilitar turnos abertos, abrir solicitações de turnos, solicitações de permuta e solicitações de folga

> [!IMPORTANT]
> Siga estas etapas somente se você optar por desabilitar turnos abertos, solicitações de turno abertas, solicitações de permuta ou solicitações de folga usando o script na seção Alterar configurações de conexão anteriormente neste artigo ou usando o cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance).[](#change-connection-settings) A conclusão desta etapa oculta a funcionalidade em Turnos. Sem essa segunda etapa, os usuários ainda verão a funcionalidade no Shifts e receberão uma mensagem de erro de "operação sem suporte" se tentarem usá-la.

Para ocultar turnos abertos, solicitações de permuta e solicitações de folga no Shifts, use o [](/graph/api/resources/schedule) tipo de recurso de agendamento API do Graph para definir os seguintes parâmetros ```false``` para cada equipe mapeada para uma instância de WFM Blue Yonder:

- Abrir turnos: ```openShiftsEnabled```
- Solicitações de permuta:  ```swapShiftsRequestsEnabled```
- Solicitações de folga: ```timeOffRequestsEnabled```

Para ocultar solicitações de turnos abertos em Turnos,  vá para Configurações em Turnos e desative a **configuração Abrir turnos**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Desmapear uma equipe de uma conexão e mapeá-la para outra conexão

> [!NOTE]
> A conta de sistema do Microsoft 365 deve ser a mesma para ambas as conexões. Se não estiver, você receberá uma mensagem de erro "Este perfil de ator designado não tem privilégios de propriedade da equipe".

Se você quiser desmapear uma equipe de uma conexão e mapeá-la para outra conexão:

1. [Configure seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso).
1. Exiba uma lista de todos os mapeamentos de equipe para uma conexão.

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

Para saber mais, confira [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) e [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).

## <a name="disable-sync-for-a-connection"></a>Desabilitar a sincronização para uma conexão

Use esse script para desabilitar a sincronização de uma conexão. Tenha em mente que esse script não remove nem exclui uma conexão. Ele desativa a sincronização para que nenhum dado seja sincronizado entre Shifts e Blue Yonder WFM para a conexão especificada.

[Configure seu ambiente](#set-up-your-environment) (caso ainda não tenha feito isso) e execute o script a seguir.

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

## <a name="shifts-connector-cmdlets"></a>Cmdlets do conector shifts

Para obter ajuda com cmdlets do conector shifts, pesquise **CsTeamsShiftsConnection** na referência [de cmdlet do PowerShell do Teams](/powershell/teams/intro). Aqui estão links para alguns cmdlets comumente usados.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>Artigos relacionados

- [Conectores de turnos](shifts-connectors.md)
- [Use o assistente do conector Shifts para conectar o Shifts ao Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usar o PowerShell para conectar o Shifts ao Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Gerenciar o aplicativo Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Visão Geral do PowerShell do Teams](../../teams-powershell-overview.md)
