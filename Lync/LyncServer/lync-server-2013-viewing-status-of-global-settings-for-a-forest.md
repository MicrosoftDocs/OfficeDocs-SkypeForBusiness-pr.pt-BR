---
title: 'Lync Server 2013: exibindo o status de configurações globais para uma floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Exibir o status das configurações globais de uma floresta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-20_

Os administradores devem analisar as configurações globais para uma implantação do Lync Server 2013 mensalmente. O objetivo seria revisar as configurações implementadas em relação a um conjunto de configurações conhecidas, uma configuração de linha de base para ajudar a garantir que as configurações sejam válidas e determinar se a documentação da linha de base deve ser atualizada. As alterações na configuração global devem ser implementadas por meio de um processo de controle de alterações que deve incluir a documentação das novas configurações.

As configurações globais que devem ser analisadas estão descritas nas seções a seguir:

<div>

## <a name="check-general-settings"></a>Verificar as configurações gerais

Verifique as configurações gerais, incluindo os domínios SIP (Session Initiation Protocol) com suporte para o Lync Server 2013.

As informações do domínio SIP podem ser retornadas usando o Windows PowerShell e o cmdlet **Get-CsSipDomain** . Para retornar essas informações, execute o `Get-CsSipDomain` comando do Windows PowerShell.

Get-CsSipDomain retornará informações semelhantes para todos os domínios SIP autorizados:

Nome da identidade-padrão

\-------- ---- ---------

fabrikam.com fabrikam.com verdadeiro

na.fabrikam.com na.fabrikam.com falso

Se a Propriedade IsDefault estiver definida como true, o domínio correspondente será o seu domínio SIP padrão. Você pode usar o cmdlet Set-CsSipDomain para alterar o domínio SIP padrão de sua organização. No entanto, você não pode apenas excluir o domínio SIP padrão porque isso o deixaria sem um domínio padrão. Se você quisesse excluir o domínio fabrikam.com (conforme mostrado no exemplo anterior), primeiro precisaria configurar na.fabrikam.com para ser o domínio padrão.

</div>

<div>

## <a name="check-meeting-settings"></a>Verificar as configurações da reunião

As configurações de reunião incluem definições de política de reunião e suporte para a participação de usuários anônimos em reuniões.

As definições de configuração de reunião podem ser recuperadas usando o Windows PowerShell e o cmdlet **Get-CsMeetingConfiguration** . Por exemplo, esse comando retorna informações sobre as definições de configuração de reunião global:

Get-CsMeetingConfiguration – as configurações de reunião "global" de identidade também podem ser configuradas no escopo do site. Por isso, talvez você queira usar o seguinte comando, que retorna informações sobre todas as definições de configuração de reunião:

`Get-CsMeetingConfiguration`

O cmdlet **Get-CsMeetingConfiguration** retorna informações semelhantes às seguintes:

Identidade: global

PstnCallersBypassLobby: true

EnableAssignedConferenceType: true

DesignateAsPresenter: empresa

AssignedConferenceTypeByDefault: true

AdmitAnonymousUsersByDefault: true

Novamente, o item final na lista, **AdmitAnonymousUsersByDefault**, habilita ou desabilita a capacidade dos usuários anônimos de participarem de reuniões.

Ao verificar as configurações de reunião, talvez seja útil comparar as configurações atuais com relação aos equivalentes padrão. Você pode visualizar as configurações de reunião padrão executando o seguinte comando:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

O comando anterior cria uma instância de configuração de reunião global somente na memória, uma instância que usa o valor padrão para cada propriedade. Nenhuma configuração de reunião real é criada quando você executa o comando. No entanto, todos os valores de propriedades padrão serão exibidos na tela.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Verificar os servidores de borda e suas configurações

As informações do servidor de borda podem ser recuperadas usando o Windows PowerShell. Esse comando retorna informações sobre todos os servidores de borda configurados para uso em sua organização:

`Get-CsService -EdgeServer`

As informações retornadas incluem todas as configurações de FQDN e de porta para cada servidor de borda:

Identidade: EdgeServer: dc.fabrikam.com

Registrador: registrar: LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 50000

MediaComunicationPortCount: 10000

AccessEdgeExternalFqdn: dc.fabrikam.com

DataEdgeExternalFqdn: dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn: dc.fabrikam.com

DependentServiceList: {registrador: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-SE. fabrikam

com, MediationServer: LYNC-SE.

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: site:fabrikam. com

PoolFqdn: dc.fabrikam.com

Versão: 5

Função: EdgeServer

<div>

## <a name="check-federation-settings"></a>Verificar as configurações de Federação

Verifique as configurações de Federação, como se ela está configurada e, se a resposta for "Sim", o FQDN e a porta. A Federação está habilitada e desabilitada usando a coleção global de definições de configuração de borda de acesso. Entre outras coisas, isso significa que a Federação está configurada com base em tudo ou nada: a Federação está habilitada para toda a organização ou a Federação está desabilitada para toda a organização

Suas configurações de borda de acesso podem ser retornadas usando o Windows PowerShell. Para fazer isso, execute o seguinte comando do Windows PowerShell:

`Get-CsAccessEdgeConfiguration`

Por sua vez, esse comando retornará dados semelhantes a isto:

Identidade: global

AllowAnonymousUsers: false

AllowFederatedUsers: false

AllowOutsideUsers: false

Myclearinghouse: falso

EnablePartnerDiscovery: false

EnableArchivingDisclaimer: false

KeepCrlsUpToDateForPeers: true

MarkSourceVerifiableOnOutgoingMessages: true

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod : UseDnsSrvRouting

Se a propriedade **AllowFederatedUsers** estiver definida como true, isso significa que a Federação está habilitada para sua organização. (Definir **AllowFederatedUsers** como true também significa que, em um cenário de domínio dividido, os usuários locais poderão se comunicar perfeitamente com seus usuários na nuvem.)

Para recuperar as configurações de FQDN e de porta do servidor de borda, consulte a tarefa anterior (servidores de borda e suas configurações).

Habilitar a Federação no escopo global apenas significa que os usuários podem se comunicar com usuários federados. Para determinar se os usuários individuais podem realmente se comunicar com usuários federados exigem que você examine a política de acesso de usuários externos atribuída a esse usuário.

As informações de acesso do usuário externo podem ser retornadas usando o Windows PowerShell. Por exemplo, esse comando retorna informações para a política de acesso externo ao usuário externo:

`Get-CsExternalAccessPolicy -Identity "Global"`

E esse comando retorna informações para todas as políticas de acesso externo do usuário:

`Get-CsExternalAccessPolicy`

As informações retornadas serão parecidas com isto:

Identidade: falso

Descritivo

EnableFederationAccess: false

EnablePublicCloudAccess: false

EnablePublicCloudAccessAudioVideoAccess: false

EnableOutsideAccess: false

Se **EnableFederationAccess** for definido como true, os usuários gerenciados pela política fornecida poderão se comunicar com os usuários federados.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Verificar as configurações de arquivamento

Verifique as configurações de arquivamento para comunicações internas e federadas. Antes de verificar as configurações de arquivamento interno e externo, verifique se o arquivamento está habilitado.

As configurações de arquivamento podem ser verificadas usando o Windows PowerShell e o cmdlet Get-CsArchivingConfiguration:

`Get-CsArchivingConfiguration -Identity "Global"`

Observe que as configurações de arquivamento também podem ser configuradas no escopo do site. Para retornar informações sobre todas as configurações de arquivamento, use este comando:

`Get-CsArchivingConfiguration`

O cmdlet Get-CsArchivingConfiguration retorna dados semelhantes a este:

Identidade: global

EnableArchiving: false

EnablePurging: false

PurgeExportedArchivesOnly: false

BlockOnArchiveFailure: false

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: true

CachePurgingInterval: 24

Se a propriedade EnableArchiving estiver definida como false, isso significa que nenhuma sessão de comunicação será arquivada. Se você quiser arquivar sessões de mensagens instantâneas somente, use um comando como o seguinte para habilitar o arquivamento de sessões de mensagens instantâneas:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Para arquivar sessões de conferência e sessões de mensagens instantâneas, use este comando:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Se quiser comparar as configurações atuais de arquivamento com as configurações padrão, execute o seguinte comando do Windows PowerShell:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Esse comando cria uma instância somente na memória das configurações de configuração global de arquivamento. Este não é um conjunto real de configurações que é usado pelo Lync Server. No entanto, ele exibe os valores padrão para todas as propriedades de configuração de arquivamento.

Você também pode usar esse comando para retornar o FQDN dos seus servidores de arquivamento:

`Get-CsService -ArchivingServer`

Depois de verificar se o arquivamento está habilitado, você pode ver as políticas de arquivamento para determinar se as sessões de comunicação internas e externas estão sendo arquivadas.

As informações da política de arquivamento podem ser recuperadas usando o cmdlet Get-CsArchivingPolicy. Por exemplo, esse comando retorna informações sobre a política de arquivamento global:

`Get-CsArchivingPolicy -Identity "Global"`

Como as políticas de arquivamento também podem ser configuradas no site e no escopo por usuário, você também pode querer usar esse comando, que retorna informações sobre todas as políticas de arquivamento:

`Get-CsArchivingPolicy`

As informações recebidas do Get-CsArchivingPolicy serão parecidas com isso:

Identidade: global

Descritivo

ArchiveInternal: false

ArchiveExternal: false

Observe que, por padrão, o arquivamento interno e externo está desabilitado em uma política de arquivamento.

</div>

<div>

## <a name="check-cdr-settings"></a>Verificar as configurações do CDR

Verifique as configurações de CDR (registro de detalhes de chamadas) para gravação ponto a ponto, conferência e detalhes de chamadas de voz. Informações detalhadas sobre as configurações do CDR podem ser retornadas usando o cmdlet **Get-CsCdrConfiguration** . Por exemplo, esse comando retorna informações sobre a coleção global de definições de configuração de CDR:

`Get-CsCdrConfiguration -Identity "Global"`

Como a CDR também pode ser configurada no escopo do site, talvez você também queira executar esse comando, que retorna informações sobre todas as definições de configuração de CDR:

`Get-CsCdrConfiguration`

O cmdlet Get-CsCdrConfiguration retorna informações parecidas com isso para cada conjunto de definições de configuração de CDR:

Identidade: global

EnableCDR: true

EnablePurging: true

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

Informações semelhantes podem ser retornadas para o monitoramento de QoE usando-se o cmdlet Get-CsQoEConfiguration. Por exemplo, esse comando retorna informações sobre a coleção global de definições de configuração de QoE:

`Get-QoEConfiguration -Identity "Global"`

Essas informações serão parecidas com isso:

Identidade: global

ExternalConsumerIssuedCertId :

EnablePurging: true

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: false

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: true

Se você quiser comparar as configurações atuais de CDR com as configurações de CDR padrão, os valores padrão podem ser revisados executando este comando:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

Da mesma forma, os valores padrão para monitoramento de QoE podem ser recuperados usando este comando:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

Você também pode retornar o FQDN dos seus servidores de monitoração executando este comando:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Verificar as configurações de voz

As configurações de voz geralmente importantes para os administradores estão contidas em políticas de voz e rotas de voz: as políticas de voz contêm as configurações que determinam os recursos expostos a usuários individuais (como a capacidade de encaminhar ou transferir chamadas), enquanto as rotas de voz determinam como as chamadas (e se) são roteadas em toda a PSTN.

As informações da política de voz podem ser recuperadas usando o Windows PowerShell. Por exemplo, esse comando retorna informações sobre a política de voz global:

`Get-CsVoicePolicy -Identity "Global"`

E esse comando retorna informações sobre todas as políticas de voz configuradas para uso na organização:

`Get-CsVoicePolicy`

As informações retornadas pelo cmdlet Get-CsVoicePolicy são semelhantes às seguintes:

Identidade: global

PstnUsages :{}

Descritivo

AllowSimulRing: true

AllowCallForwarding: true

AllowPSTNReRouting: true

Nome: DefaultPolicy

EnableDelegation: true

EnableTeamCall: true

EnableCallTransfer: true

EnableCallPark: false

EnableMaliciousCallTracing: false

EnableBWPolicyOverride: false

PreventPSTNTollBypass: false

Você também pode criar consultas que retornaram um subconjunto de suas políticas de voz. Por exemplo, esse comando retorna todas as políticas de voz que permitem o encaminhamento de chamadas:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

E esse comando retorna todas as políticas de voz que não permitem o encaminhamento de chamadas:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

No Windows PowerShell, use o cmdlet Get-CsVoiceRouting para retornar informações sobre suas rotas de voz:

`Get-CsVoiceRoute`

Esse comando retorna informações como esta para todas as rotas de voz:

Identidade: LocalRoute

Prioridade: 0

Descritivo

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages :{}

PstnGatewayList :{}

Nome: LocalRoute

SuppressCallerId :

AlternateCallerId :

O Lync Server permite criar rotas de voz que não têm um uso PSTN e não especificam um gateway PSTN. No entanto, você não pode realmente rotear chamadas por uma rota de voz que não tenha esses dois valores de propriedade configurados. Por isso, talvez seja útil executar esse comando periodicamente, que retorna a identidade de qualquer rota de voz que não tenha um uso PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

Da mesma forma, esse comando retorna a identidade de qualquer rota de voz que não tenha sido configurada para ter um gateway PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Verificar as configurações do atendedor de conferências

Verifique as configurações do atendedor de conferências para conferências discadas PSTN. As configurações do atendedor de conferência só podem ser recuperadas usando o cmdlet **Get-CsDialInConferencingConfiguration** . Essas configurações não estão disponíveis no painel de controle do Lync Server. Para exibir as configurações do atendedor de conferência, use um comando do Windows PowerShell semelhante ao seguinte, que retorna a coleção global das configurações do atendedor de conferência:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Observe que as configurações do atendedor de conferências também podem ser configuradas no escopo do site. Para retornar informações sobre todas as configurações do atendedor de conferência, use este comando em vez disso:

`Get-CsDialInConferencingConfiguration`

O cmdlet Get-CsDialInConferencingConfiguration retorna dados semelhantes a este:

Identidade: global

EntryExitAnnouncementsType : UseNames

EnableNameRecording: true

EntryExitAnnouncementsEnabledByDefault: false

Se EntryExitAnnouncementsEnabledByDefault estiver definido como false, isso significa que os comunicados de conferência estão desabilitados. Para habilitar os comunicados de entrada e saída, execute um comando do Windows PowerShell semelhante a este:

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

