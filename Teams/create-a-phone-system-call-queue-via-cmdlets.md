---
title: Criar uma fila de chamada por meio de cmdlets
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Saiba como configurar filas de chamada por meio de cmdlets
ms.openlocfilehash: 8ffbef5541a230755bb7439507e3002a5cb92462
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071103"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Criar uma fila de chamada por meio de cmdlets

## <a name="assumptions"></a>Suposições
1)  O PowerShell está instalado em seu computador
- Configurar seu computador para [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
- Módulo MSTeams Instalado ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Módulo MSOnline instalado ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Você tem direitos de administração de locatários
3)  Você comprou Microsoft Teams Telefone
4)  Os agentes, listas de distribuição e Teams canais referidos abaixo já foram criados

Observação: o cmdlet Teams Channel usado abaixo faz parte da versão visualização pública do módulo Teams PowerShell.  Para obter mais informações, consulte Install Teams Public Preview do [PowerShell](teams-powershell-install.md) e também consulte Microsoft Teams Notas de Versão [do PowerShell.](teams-powershell-release-notes.md)

Os usuários que já têm o módulo MicrosoftTeams instalado devem garantir que a versão mais atualizada ````Update-Module MicrosoftTeams```` seja instalada.


## <a name="scenario"></a>Cenário

As três filas de chamada a seguir serão criadas:

Informações da Fila de Chamada de Vendas:
- Fronted by Atendedor Automático: Sim
- Chamada direta do PSTN: Não
- Idioma: Inglês DOS EUA
- Saudação: Nenhum
- Música em espera: reproduzir um arquivo de áudio
- - Nome do arquivo: sales-hold-in-queue-music.wav
- Atendimento de chamada: Usuários
- - Bill@contoso.com
- - Mary@contoso.com
- Modo de Conferência: On
- Método de roteamento: Attendant
- Roteamento baseado em presença: desligado
- Os agentes de chamada podem optar por não atender chamadas: Sim
- Tempo de alerta do agente de chamada: 15
- Tratamento de estouro de chamada: 200
- - Redirecionar para: Adele@contoso.com
- Tratamento de tempo de tempo de chamada: 120 segundos
- - Redirecionar para: Adele@contoso.com

Suporte a informações da Fila de Chamada:
- Fronted by Atendedor Automático: Sim
- Chamada direta do PSTN: Não
-   Idioma: Inglês Reino Unido
-   Saudação: reproduzir um arquivo de áudio
-   - Nome do arquivo: support-greeting.wav
-   Música em espera: reproduzir um arquivo de áudio
-   - Nome do arquivo: support-hold-in-queue-music.wav
-   Atendimento de chamada: Lista de distribuição de suporte
-   - Support@contoso.com
-   Modo de Conferência: On
-   Método routing: Longest Idle
-   Roteamento baseado em presença: N/A – on por padrão devido a Longest Idle
-   Os agentes de chamada podem optar por não atender chamadas: Não
-   Tempo de alerta do agente de chamada: 15
-   Tratamento de estouro de chamada: 200
-   - Redirecionamento: Suporte a Caixa Postal Compartilhada
- - -   Reproduzir um arquivo de áudio (support-shared-voicemail-greeting.wav)
- - -   Transcrição habilitada
-   Tratamento de tempo de tempo de chamada: 45 minutos
-   - Redirecionamento: Suporte a Caixa Postal Compartilhada
- - - TTS: "Lamentamos tê-lo mantido esperando e agora estamos transferindo sua chamada para a caixa postal."
- - - Transcrição habilitada


Informações da Fila de Chamada Colaborativa de Instalações:
- Fronted by Atendedor Automático: Não
- Chamada direta do PSTN: Não (somente chamada interna)
-   Idioma: FR francês
-   Saudação: Nenhum
-   Música em espera: padrão
-   Atendimento de chamada: Equipe: Instalações
-   Canal de Atendimento de Chamada: Help Desk
-   - Proprietário do canal: Fred@contoso.com
-   Modo de Conferência: On
-   Método routing: Round Robin
-   Roteamento baseado em presença: On
-   Os agentes de chamada podem optar por não atender chamadas: Não
-   Tempo de alerta do agente de chamada: 15
-   Tratamento de estouro de chamada: 200
-   - Desconectar
-   Tratamento de tempo de tempo de chamada: 45 minutos
-   - Desconectar


## <a name="login"></a>Login
Você será solicitado a inserir suas credenciais Teams administrador.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>Fila de Vendas
### <a name="create-audio-files"></a>Criar arquivos de áudio
Substitua "d:" \\ pelo caminho para onde os arquivos wav são armazenados em seu computador.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Obter ID de Usuários
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>Obter lista de idiomas com suporte
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Criar Fila de Chamada
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obter tipos de licença
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Criar e atribuir conta de recurso
Observação: Telefone número não obrigatório aqui, pois a fila de chamada está na frente terminada por um Atendedor Automático
- ApplicationID
- - Atendedor Automático: ce933385-9390-45d1-9512-c8d228074e07
- - Fila de Chamada: 11cd3e2e-fccb-42ad-ad00-878b93575e07

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>Fila de Suporte
### <a name="create-audio-files"></a>Criar arquivos de áudio
Substitua "d:" \\ pelo caminho para onde os arquivos wav são armazenados em seu computador.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Obter ID do grupo de equipe de suporte
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Obter lista de idiomas com suporte
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Criar Fila de Chamada
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obter tipos de licença
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Criar e atribuir conta de recurso
Observação: Telefone número não obrigatório aqui, pois a fila de chamada é front-ended por um Atendedor Automático
- ApplicationID
- - Atendedor Automático: ce933385-9390-45d1-9512-c8d228074e07
- - Fila de Chamada: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>Fila de Chamada Colaborativa de Instalações
### <a name="get-facilities-team-group-id"></a>Obter ID do grupo de equipe de instalações
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Obter ID do canal de equipe do Help Desk de Instalações
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>Obter ID do usuário do canal de Ajuda de Instalações
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Obter em nome da ID da conta de recurso de chamada
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>Obter lista de idiomas com suporte
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Criar Fila de Chamada
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Obter tipos de licença
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Criar e atribuir conta de recurso
Observação: Telefone número não obrigatório aqui, pois a fila de chamada é front-ended por um Atendedor Automático
- ApplicationID
- - Atendedor Automático: ce933385-9390-45d1-9512-c8d228074e07
- - Fila de Chamada: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
