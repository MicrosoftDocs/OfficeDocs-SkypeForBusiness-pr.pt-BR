---
title: Criar uma fila de chamadas por meio de cmdlets
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
description: Saiba como configurar filas de chamadas por meio de cmdlets
ms.openlocfilehash: bdaf538164a74a366779bd3a4928330a2bc3b085
ms.sourcegitcommit: c06d806778f3e6ea4b184bae271e55c34fd9594d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65244898"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Criar uma fila de chamadas por meio de cmdlets

## <a name="assumptions"></a>Suposições
1)  O PowerShell está instalado no computador
- Configure seu computador para [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
- Módulo MSTeams instalado ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Módulo MSOnline instalado ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Você tem direitos de administração de locatário
3)  Você comprou Telefonia do Microsoft Teams
4)  Os agentes, listas de distribuição e Teams canais mencionados abaixo já foram criados

Observação: o cmdlet Teams Channel usado abaixo faz parte da versão de Visualização Pública do Teams PowerShell.  Para obter mais informações, [consulte Instalar Teams visualização pública do PowerShell](teams-powershell-install.md) e também consulte [Microsoft Teams notas de versão do PowerShell](teams-powershell-release-notes.md).

Os usuários que já têm o módulo MicrosoftTeams ````Update-Module MicrosoftTeams```` instalado devem garantir que a versão mais atualizada esteja instalada.


## <a name="scenario"></a>Cenário

As três filas de chamadas a seguir serão criadas:

Informações da Fila de Chamadas de Vendas:
- Fronted by Auto Attendant: Yes
- Chamada direta de PSTN: Não
- Idioma: Inglês dos EUA
- Saudação: Nenhum
- Música em espera: reproduzir um arquivo de áudio
- - Nome do arquivo: sales-hold-in-queue-music.wav
- Atendimento de chamadas: usuários
- - Bill@contoso.com
- - Mary@contoso.com
- Modo de Conferência: Ativado
- Método de roteamento: Attendant
- Roteamento baseado em presença: desativado
- Os agentes de chamada podem recusar a chamada: Sim
- Tempo de alerta do agente de chamada: 15
- Tratamento de estouro de chamada: 200
- - Redirecionar para: Adele@contoso.com
- Tratamento de tempo limite de chamada: 120 segundos
- - Redirecionar para: Adele@contoso.com

Informações da Fila de Chamadas de Suporte:
- Fronted by Auto Attendant: Yes
- Chamada direta de PSTN: Não
-   Idioma: Inglês do Reino Unido
-   Saudação: reproduzir um arquivo de áudio
-   - Nome do arquivo: support-greeting.wav
-   Música em espera: reproduzir um arquivo de áudio
-   - Nome do arquivo: support-hold-in-queue-music.wav
-   Atendimento de chamadas: lista de distribuição de suporte
-   - Support@contoso.com
-   Modo de Conferência: Ativado
-   Método de roteamento: Ocioso Mais Longo
-   Roteamento baseado em presença: N/A – ativado por padrão devido à ociosidade mais longa
-   Os agentes de chamada podem recusar a chamada: Não
-   Tempo de alerta do agente de chamada: 15
-   Tratamento de estouro de chamada: 200
-   - Redirecionamento: suporte à caixa postal compartilhada
- - -   Reproduzir um arquivo de áudio (support-shared-voicemail-greeting.wav)
- - -   Transcrição habilitada
-   Tratamento de tempo limite de chamada: 45 minutos
-   - Redirecionamento: suporte à caixa postal compartilhada
- - - TTS: "Lamentamos ter mantido você esperando e agora está transferindo sua chamada para a caixa postal."
- - - Transcrição habilitada


Informações da Fila de Chamadas Colaborativas do Facilities:
- Fronted by Auto Attendant: No
- Chamada direta de PSTN: Não (somente chamada interna)
-   Idioma: FRANCÊS FR
-   Saudação: Nenhum
-   Música em espera: padrão
-   Atendimento de chamadas: Equipe: Instalações
-   Canal de Atendimento de Chamadas: Suporte Técnica
-   - Proprietário do canal: Fred@contoso.com
-   Modo de Conferência: Ativado
-   Método de roteamento: Round Robin
-   Roteamento baseado em presença: ativado
-   Os agentes de chamada podem recusar a chamada: Não
-   Tempo de alerta do agente de chamada: 15
-   Tratamento de estouro de chamada: 200
-   - Desconectar
-   Tratamento de tempo limite de chamada: 45 minutos
-   - Desconectar


## <a name="login"></a>Login
Você será solicitado a inserir suas credenciais de Teams administrador.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>Fila de Vendas
### <a name="create-audio-files"></a>Criar arquivos de áudio
Substitua "d:\\" pelo caminho para onde os arquivos wav são armazenados no computador.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Obter ID de Usuários
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).Identity
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).Identity
````

### <a name="get-list-of-supported-languages"></a>Obter lista de idiomas com suporte
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Criar Fila de Chamadas
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obter tipos de licença
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Criar e atribuir conta de recurso
Observação: Telefone número não necessário aqui, pois a fila de chamadas é encerrada com frente por um Atendedor Automático
- Applicationid
- - Atendedor Automático: ce933385-9390-45d1-9512-c8d228074e07
- - Fila de Chamadas: 11cd3e2e-fcb-42ad-ad00-878b93575e07

Observação: o tipo de licença mostrado abaixo (PHONESYSTEM_VIRTUALUSER) deve ser aquele listado pela Get-MsolAccountSku cmdlet acima.

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>Fila de Suporte
### <a name="create-audio-files"></a>Criar arquivos de áudio
Substitua "d:\\" pelo caminho para onde os arquivos wav são armazenados no computador.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Obter a ID do grupo de equipe de suporte
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Obter lista de idiomas com suporte
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Criar Fila de Chamadas
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obter tipos de licença
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Criar e atribuir conta de recurso
Observação: Telefone número não necessário aqui, pois a fila de chamadas é front-end por um Atendedor Automático
- Applicationid
- - Atendedor Automático: ce933385-9390-45d1-9512-c8d228074e07
- - Fila de Chamadas: 11cd3e2e-fcb-42ad-ad00-878b93575e07

Observação: o tipo de licença mostrado abaixo (PHONESYSTEM_VIRTUALUSER) deve ser aquele listado pela Get-MsolAccountSku cmdlet acima.

````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>Fila de Chamadas Colaborativas de Instalações
### <a name="get-facilities-team-group-id"></a>Obter a ID do grupo de equipe do Facilities
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Obter a ID do canal da equipe do Suporte Técnica do Facilities
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Obter a ID de usuário do proprietário do canal do Facilities Help Desk
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Obter em nome da ID da conta de recurso de chamada
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
````

### <a name="get-list-of-supported-languages"></a>Obter lista de idiomas com suporte
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Criar Fila de Chamadas
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Obter tipos de licença
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Criar e atribuir conta de recurso
Observação: Telefone número não necessário aqui, pois a fila de chamadas é front-end por um Atendedor Automático
- Applicationid
- - Atendedor Automático: ce933385-9390-45d1-9512-c8d228074e07
- - Fila de Chamadas: 11cd3e2e-fcb-42ad-ad00-878b93575e07

Observação: o tipo de licença mostrado abaixo (PHONESYSTEM_VIRTUALUSER) deve ser aquele listado pela Get-MsolAccountSku cmdlet acima.

````
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
