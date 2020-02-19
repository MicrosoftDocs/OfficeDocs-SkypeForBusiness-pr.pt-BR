---
title: 'Lync Server 2013: exibindo o status das configurações globais de uma floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540ce07a106e583f3ea0d4b523e1cf882677c19b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Exibir o status das configurações globais de uma floresta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-20_

Os administradores devem examinar as configurações globais de uma implantação do Lync Server 2013 mensal. O objetivo seria examinar as configurações implementadas em um conjunto de configurações conhecidas, uma configuração de linha de base para ajudar a garantir que as configurações sejam válidas e para determinar se a documentação da linha de base deve ser atualizada. As alterações na configuração global devem ser implementadas por meio de um processo de controle de alterações que deve incluir a documentação das novas configurações.

As configurações globais que devem ser analisadas são descritas nas seções a seguir:

<div>

## <a name="check-general-settings"></a>Verificar configurações gerais

Verifique as configurações gerais, incluindo os domínios SIP (Session Initiation Protocol) suportados para o Lync Server 2013.

As informações do domínio SIP podem ser retornadas usando o Windows PowerShell e o cmdlet **Get-CsSipDomain** . Para retornar essas informações, execute o `Get-CsSipDomain` comando do Windows PowerShell.

O Get-CsSipDomain retornará informações semelhantes a estas para todos os domínios SIP autorizados:

Nome da identidade IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com true

na.fabrikam.com na.fabrikam.com falso

Se a Propriedade IsDefault estiver definida como true, o domínio correspondente será seu domínio SIP padrão. Você pode usar o cmdlet Set-CsSipDomain para alterar o domínio SIP padrão para sua organização. No entanto, você não pode simplesmente excluir o domínio SIP padrão, pois isso deixaria sem um domínio padrão. Se você quisesse excluir o domínio fabrikam.com (conforme mostrado no exemplo anterior), você primeiro precisaria configurar o na.fabrikam.com para ser seu domínio padrão.

</div>

<div>

## <a name="check-meeting-settings"></a>Verificar configurações de reunião

As configurações de reunião incluem definições de política de reunião e suporte para participação de usuários anônimos em reuniões.

As definições de configuração de reunião podem ser recuperadas usando o Windows PowerShell e o cmdlet **Get-CsMeetingConfiguration** . Por exemplo, este comando retorna informações sobre as definições de configuração de reunião global:

Get-CsMeetingConfiguration – Identity "global" as definições de configuração de reunião também podem ser configuradas no escopo do site. Por isso, talvez você queira usar o seguinte comando, que retorna informações sobre todas as definições de configuração de reunião:

`Get-CsMeetingConfiguration`

O cmdlet **Get-CsMeetingConfiguration** retorna informações semelhantes às seguintes:

Identity: global

PstnCallersBypassLobby: true

EnableAssignedConferenceType: true

DesignateAsPresenter: empresa

AssignedConferenceTypeByDefault: true

AdmitAnonymousUsersByDefault: true

Novamente, o item final na lista, **AdmitAnonymousUsersByDefault**, habilita ou desabilita a capacidade de usuários anônimos participarem de reuniões.

Ao verificar as definições de configuração da reunião, pode ser útil comparar as configurações atuais com os equivalentes padrão. Você pode exibir as definições de configuração de reunião padrão executando o seguinte comando:

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

O comando anterior cria uma instância somente na memória das definições de configuração de reunião global, uma instância que usa o valor padrão para cada propriedade. Nenhuma configuração real de reunião é criada quando você executa o comando. No entanto, todos os valores de propriedade padrão serão exibidos na tela.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Verificar servidores de borda e suas configurações

As informações do servidor de borda podem ser recuperadas usando o Windows PowerShell. Este comando retorna informações sobre todos os servidores de borda configurados para uso na sua organização:

`Get-CsService -EdgeServer`

As informações retornadas incluem todas as configurações de FQDN e de porta para cada servidor de borda:

Identidade: EdgeServer: dc.fabrikam.com

Registrador: registrador: LYNC-SE.fabrikam.com

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

DependentServiceList: {registrar: LYNC-SE.fabrikam.com,

ConferencingServer: LYNC-SE. fabrikam

com, MediationServer: LYNC-SE.

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: site:fabrikam. com

PoolFqdn: dc.fabrikam.com

Versão: 5

Função: EdgeServer

<div>

## <a name="check-federation-settings"></a>Verificar configurações de Federação

Verifique as configurações de Federação, por exemplo, se ela está configurada e, se a resposta for "Sim", o FQDN e a porta. A Federação é habilitada e desabilitada usando o conjunto global de definições de configuração de borda de acesso. Entre outras coisas, isso significa que a Federação é configurada em uma base de tudo ou nada: a Federação está habilitada para toda a organização ou a Federação está desabilitada para toda a organização

Suas definições de configuração de borda de acesso podem ser retornadas usando o Windows PowerShell. Para fazer isso, execute o seguinte comando do Windows PowerShell:

`Get-CsAccessEdgeConfiguration`

Por sua vez, esse comando retornará dados similares a estes:

Identity: global

AllowAnonymousUsers: falso

AllowFederatedUsers: falso

AllowOutsideUsers: falso

Beclearinghouse: falso

EnablePartnerDiscovery: falso

EnableArchivingDisclaimer: falso

KeepCrlsUpToDateForPeers: true

MarkSourceVerifiableOnOutgoingMessages: true

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

Se a propriedade **AllowFederatedUsers** estiver definida como true, isso significa que a Federação está habilitada para sua organização. (A configuração de **AllowFederatedUsers** como true também significa que, em um cenário de domínio dividido, seus usuários locais poderão se comunicar sem problemas com seus usuários na nuvem.)

Para recuperar as configurações de FQDN e de porta do servidor de borda, confira a tarefa anterior (servidores de borda e suas configurações).

Habilitar a Federação no escopo global significa que os usuários podem se comunicar potencialmente com usuários federados. Para determinar se os usuários individuais podem realmente se comunicar com os usuários federados exigem que você examine a política de acesso de usuário externo atribuída a esse usuário.

As informações de acesso de usuário externo podem ser retornadas usando o Windows PowerShell. Por exemplo, este comando retorna informações sobre a política de acesso de usuário externo global:

`Get-CsExternalAccessPolicy -Identity "Global"`

E este comando retorna informações de todas as políticas de acesso de usuário externo:

`Get-CsExternalAccessPolicy`

As informações retornadas serão parecidas com:

Identity: false

Descrição

EnableFederationAccess: falso

EnablePublicCloudAccess: falso

EnablePublicCloudAccessAudioVideoAccess: falso

EnableOutsideAccess: falso

Se **EnableFederationAccess** for definido como true, os usuários gerenciados pela política determinada poderão se comunicar com os usuários federados.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Verificar configurações de arquivamento

Verifique as configurações de arquivamento para comunicações internas e federadas. Antes de verificar as configurações de arquivamento interno e externo, você deve verificar se o arquivamento está habilitado.

As definições de configuração de arquivamento podem ser verificadas usando o Windows PowerShell e o cmdlet Get-CsArchivingConfiguration:

`Get-CsArchivingConfiguration -Identity "Global"`

Observe que as configurações de arquivamento também podem ser configuradas no escopo do site. Para retornar informações sobre todas as configurações de arquivamento, use este comando:

`Get-CsArchivingConfiguration`

O cmdlet Get-CsArchivingConfiguration retorna dados similares a estes:

Identity: global

EnableArchiving: falso

EnablePurging: falso

PurgeExportedArchivesOnly: falso

BlockOnArchiveFailure: falso

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: true

CachePurgingInterval: 24

Se a propriedade EnableArchiving estiver definida como false, isso significa que nenhuma sessão de comunicação será arquivada. Se você deseja arquivar somente sessões de mensagens instantâneas, use um comando como o seguinte para habilitar o arquivamento de sessões de IM:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Para arquivar sessões de conferência e sessões de mensagens instantâneas, use este comando:

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Se você quiser comparar suas configurações de arquivamento atuais com as configurações padrão, execute o seguinte comando do Windows PowerShell:

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Esse comando cria uma instância somente na memória das definições de configuração de arquivamento global. Este não é um conjunto real de configurações que é usado pelo Lync Server. No entanto, ele exibe os valores padrão para todas as propriedades de configuração de arquivamento.

Você também pode usar este comando para retornar o FQDN dos seus servidores de arquivamento:

`Get-CsService -ArchivingServer`

Depois de verificar se o arquivamento está habilitado, você pode exibir suas políticas de arquivamento para determinar se as sessões de comunicação interna e externa estão sendo arquivadas.

As informações de política de arquivamento podem ser recuperadas usando o cmdlet Get-CsArchivingPolicy. Por exemplo, este comando retorna informações sobre a política de arquivamento global:

`Get-CsArchivingPolicy -Identity "Global"`

Como as políticas de arquivamento também podem ser configuradas no site e no escopo por usuário, você também pode querer usar este comando, que retorna informações sobre todas as políticas de arquivamento:

`Get-CsArchivingPolicy`

As informações recebidas do Get-CsArchivingPolicy serão parecidas com isso:

Identity: global

Descrição

ArchiveInternal: falso

ArchiveExternal: falso

Observe que, por padrão, o arquivamento interno e externo está desabilitado em uma política de arquivamento.

</div>

<div>

## <a name="check-cdr-settings"></a>Verificar configurações de CDR

Verifique as configurações de CDR (registro de detalhes de chamadas) para gravação de detalhes de chamada de voz e ponto a ponto. Informações detalhadas sobre as configurações de CDR podem ser retornadas usando o cmdlet **Get-CsCdrConfiguration** . Por exemplo, este comando retorna informações sobre o conjunto global de definições de configuração de CDR:

`Get-CsCdrConfiguration -Identity "Global"`

Como o CDR também pode ser configurado no escopo do site, você também pode querer executar este comando, que retorna informações sobre todas as definições de configuração de CDR:

`Get-CsCdrConfiguration`

O cmdlet Get-CsCdrConfiguration retorna informações parecidas com isso para cada conjunto de definições de configuração de CDR:

Identity: global

EnableCDR: true

EnablePurging: true

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

Informações semelhantes podem ser retornadas para monitoramento de QoE usando o cmdlet Get-CsQoEConfiguration. Por exemplo, este comando retorna informações sobre o conjunto global de definições de configuração de QoE:

`Get-QoEConfiguration -Identity "Global"`

Essa informação será semelhante a esta:

Identity: global

ExternalConsumerIssuedCertId :

EnablePurging: true

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: falso

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE: true

Se você deseja comparar suas configurações de CDR atuais com as configurações de CDR padrão, os valores padrão podem ser revisados executando este comando:

`New-CsCdrConfiguration -Identity "Global" -InMemory`

Da mesma forma, os valores padrão para monitoramento de QoE podem ser recuperados usando este comando:

`New-CsQoEConfiguration -Identity "Global" -InMemory`

Você também pode retornar o FQDN dos seus servidores de monitoramento executando este comando:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Verificar configurações de voz

As configurações de voz normalmente importantes para os administradores estão contidas em políticas de voz e rotas de voz: as políticas de voz contêm as configurações que determinam os recursos expostos a usuários individuais (como a capacidade de encaminhar ou transferir chamadas), enquanto as rotas de voz determinam como as chamadas (e se) são encaminhadas no PSTN.

As informações da política de voz podem ser recuperadas usando o Windows PowerShell. Por exemplo, este comando retorna informações sobre a política de voz global:

`Get-CsVoicePolicy -Identity "Global"`

E este comando retorna informações sobre todas as políticas de voz configuradas para uso na organização:

`Get-CsVoicePolicy`

As informações retornadas pelo cmdlet Get-CsVoicePolicy se assemelham ao seguinte:

Identity: global

PstnUsages{}

Descrição

AllowSimulRing: true

AllowCallForwarding: true

AllowPSTNReRouting: true

Nome: DefaultPolicy

EnableDelegation: true

EnableTeamCall: true

EnableCallTransfer: true

EnableCallPark: falso

EnableMaliciousCallTracing: falso

EnableBWPolicyOverride: falso

PreventPSTNTollBypass: falso

Você também pode criar consultas que retornaram um subconjunto de suas políticas de voz. Por exemplo, este comando retorna todas as políticas de voz que permitem o encaminhamento de chamadas:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

E este comando retorna todas as políticas de voz que não permitem o encaminhamento de chamadas:

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

No Windows PowerShell, use o cmdlet Get-CsVoiceRouting para retornar informações sobre suas rotas de voz:

`Get-CsVoiceRoute`

Esse comando retorna informações como esta para todas as rotas de voz:

Identidade: LocalRoute

Prioridade: 0

Descrição

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages{}

PstnGatewayList :{}

Nome: LocalRoute

SuppressCallerId :

AlternateCallerId :

O Lync Server permite que você crie rotas de voz que não têm um uso PSTN e não especificam um gateway PSTN. No entanto, você não pode rotear chamadas por uma rota de voz que não tenha esses dois valores de propriedade configurados. Por causa disso, você pode achar útil executar este comando periodicamente, que retorna a identidade de qualquer rota de voz que não tenha um uso de PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

Da mesma forma, este comando retorna a identidade de qualquer rota de voz que não tenha sido configurada para ter um gateway PSTN:

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Verificar configurações de atendedor de conferência

Verifique as configurações de atendedor de conferência para conferência discada PSTN. As configurações de atendedor de conferência só podem ser recuperadas usando o cmdlet **Get-CsDialInConferencingConfiguration** . Essas configurações não estão disponíveis no painel de controle do Lync Server. Para exibir suas configurações de atendedor de conferência, use um comando do Windows PowerShell semelhante ao seguinte, que retorna o conjunto global de configurações de atendedor de conferência:

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Observe que as configurações do atendedor de conferência também podem ser configuradas no escopo do site. Para retornar informações sobre todas as configurações de atendedor de conferência, use este comando em vez disso:

`Get-CsDialInConferencingConfiguration`

O cmdlet Get-CsDialInConferencingConfiguration retorna dados similares a estes:

Identity: global

EntryExitAnnouncementsType: UseNames

EnableNameRecording: true

EntryExitAnnouncementsEnabledByDefault: falso

Se EntryExitAnnouncementsEnabledByDefault estiver definido como false, isso significa que os comunicados de conferência estão desabilitados. Para habilitar os anúncios de entrada e saída, execute um comando do Windows PowerShell semelhante a este:

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

