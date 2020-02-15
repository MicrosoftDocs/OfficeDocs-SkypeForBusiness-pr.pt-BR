---
title: 'Lync Server 2013: atributos e descrições de esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc1d6f5041564c1b865e49ef73a539f3addb75dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Atributos e descrições de esquema no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

Esta seção descreve todos os atributos de esquema usados pelo Lync Server 2013. Para as classes associadas a atributos, confira [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Para obter uma lista de classes e atributos que são novos no Lync Server 2013, consulte [Schema Changes in Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Os atributos que são pares vinculados são especificados como links de encaminhamento ou links de volta. Um atributo que se refere a outro objeto é um vínculo progressivo; o atributo do outro objeto que se refere novamente ao primeiro objeto é um vínculo inverso. Os links de encaminhamento são atualizáveis, enquanto os links de volta são somente leitura.

Alguns atributos têm um valor de máscara de bits. Para esses atributos, cada configuração é representada por um bit e o valor decimal exibido representa a posição de bit. As posições de bit começam com bit 0. Por exemplo, 1 (binário) é bit 0 definido e 10000 (binário) é um bit 4 definido. Cada bit representa uma propriedade. Estes são alguns exemplos:

  - 10000 (binário) tem um valor decimal de 16 (ou seja, o bit 4 é definido).

  - 100 milhões (binário) tem um valor decimal de 256 (ou seja, o bit 8 é definido).

  - 1100 (binário) tem um valor decimal de 12 (ou seja, os bits 2 e 3 são definidos; as propriedades representadas por ambos os bits estão habilitadas).

  - 1111000001 (binário) tem um valor decimal de 961 (ou seja, os bits 0, 6, 7, 8 e 9 são definidos; as propriedades de cada um desses bits estão habilitadas).

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Atributos de esquema para o Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descrição</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Um atributo existente nos serviços de domínio do Active Directory que agora está associado às classes <strong>msRTCSIP-pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> . Este atributo especifica o FQDN (nome de domínio totalmente qualificado) de um pool ou de um servidor de monitoramento.</p>
<p>Um valor válido para cada segmento é 63 caracteres; um valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Este atributo contém a representação de cadeia de caracteres do DN (nome diferenciado) do objeto em outra floresta que corresponde a esse objeto. Este atributo é usado para expansão de grupo de distribuição e presença automática. Esse atributo é definido no esquema padrão do Active Directory para o Windows Server 2003 R2.</p>
<p>Para evitar a necessidade de uma atualização do AD DS para o Windows Server 2003 R2, a preparação do esquema do Active Directory estende o esquema do Windows Server 2003 com essa definição de atributo.</p></td>
<td><p>Novo no Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Este atributo com valores múltiplos contém configurações de caixa postal. Este atributo é compartilhado com a Unificação de mensagens (UM) do Exchange.</p></td>
<td><p>Novo no Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário. Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção. Este atributo é compartilhado com o Exchange 2013.</p></td>
<td><p>Novo no Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Este atributo armazena informações do provedor de audioconferência para um usuário.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Este atributo aponta para a entrada de serviço confiável para o contato de aplicativo.</p></td>
<td><p>Novo no Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>Este atributo contém uma lista de aplicativos hospedados no servidor de aplicativos.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Este atributo especifica as opções para o contato de aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Este atributo contém o idioma principal para o contato de aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Este atributo de vários valores contém os idiomas secundários para o contato de aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Este atributo contém uma lista de servidores de aplicativos que pertencem a esse pool. O vínculo sequencial correspondente a este atributo de vínculo inverso é <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Este atributo aponta para o pool ao qual pertence este servidor de aplicativos. Este é o link de encaminhamento. O vínculo inverso correspondente é <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (obsoleto)</p></td>
<td><p>Este atributo especifica o padrão global dentro do limite da floresta para o arquivamento de todas as comunicações do usuário. Isso é imposto pela camada do agente de arquivamento. O intervalo de valores para esse atributo é o seguinte:</p>
<ul>
<li><p><strong>True</strong>: arquivar todos os usuários</p></li>
<li><p><strong>False</strong>: Não arquivar todos os usuários</p></li>
</ul>
<p>Este atributo controla globalmente, dentro do limite da floresta, como as comunicações do usuário em uma rede interna são arquivadas.</p>
<p><strong>Comportamento do Live Communications Server 2005 (agora desativado)</strong></p>
<p>O intervalo de valores para esse atributo é o seguinte:</p>
<ul>
<li><p>0: arquivar o corpo da mensagem [bit 0]</p></li>
<li><p>1: não arquiva o corpo da mensagem [bit 0]</p></li>
</ul>
<p><strong>Comportamento do Office Communications Server 2007</strong></p>
<p>O intervalo de valores para esse atributo é o seguinte:</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (desativado)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Este atributo é um inteiro usado como um campo de bits para controlar se as comunicações de um único usuário devem ser arquivadas. Esse controle é imposto pela camada do agente de arquivamento. Ele está marcado para replicação do catálogo global.</p>
<p>O escopo desse atributo é específico para um único usuário ou contato. Os valores válidos (e posições de bit associadas) no Lync Server são os seguintes:</p>
<ul>
<li><p>0: Não arquivar (sem conjunto de bits)</p></li>
<li><p>1: desativado (posição de bit 0)</p></li>
<li><p>2: desativado (posição de bit 1)</p></li>
<li><p>4: Arquivar comunicações internas (posição de bit 2)</p></li>
<li><p>8: Arquivar comunicações federadas (posição de bit 3)</p></li>
</ul>
<p>Os valores válidos anteriormente no Live Communications Server 2005 são os seguintes:</p>
<ul>
<li><p>0: Use o valor padrão definido pelo <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation</strong> nesta ordem de precedência:</p>
<ul>
<li><p>1: arquivar</p></li>
<li><p>2: Não arquivar</p></li>
<li><p>3: arquivar sem o corpo da mensagem</p></li>
</ul></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (obsoleto)</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (obsoleto)</p></td>
<td><p>Este atributo define a versão do serviço de arquivamento. Este atributo é um tipo inteiro de monotonously que aumenta com cada versão oficial do produto. Os valores válidos possíveis são:</p>
<ul>
<li><p>Indefinido: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 with SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Este atributo especifica o FQDN do servidor back-end do pool. Como só pode haver um único servidor back-end por pool, este é um atributo de valor único.</p>
<p>O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Este atributo contém o identificador do pool que hospeda o diretório de conferências.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Este atributo contém o identificador de um diretório de conferência.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Este atributo contém o identificador do pool ao qual o diretório de conferência está sendo movido.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-padrão</p></td>
<td><p>Este atributo booliano define se o uso do telefone é um uso padrão. Se esse atributo for definido como <strong>true</strong>, o uso de telefone será um uso padrão e não poderá ser excluído pelo administrador. Se esse atributo for definido como <strong>false</strong>, o uso poderá ser excluído.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Este atributo identifica a URL do Communicator Web Access para usuários que estão fora da organização.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Este atributo identifica a URL do Communicator Web Access para usuários que estão dentro da organização.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsoleto)</p></td>
<td><p>Este atributo de valor único contém o nome diferenciado (DN) de um objeto de classe de perfil de local atribuído a ele.</p>
<p>Link encaminhar: <strong>link ID 11036</strong></p>
<p>O vínculo inverso correspondente é <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsoleto)</p></td>
<td><p>Este atributo booliano especifica se a política é uma política padrão. A política é uma política padrão quando definida como <strong>true</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</p></td>
<td><p>Este atributo especifica o FQDN do servidor de borda que executa o serviço de borda de acesso, se ele puder ser acessado diretamente ou do balanceador de carga de hardware para um pool de servidores que executam o serviço de borda de acesso. Se os servidores que executam o serviço de borda de acesso podem ser acessados apenas por um ou mais directors, este atributo especifica o FQDN e, opcionalmente, o número da porta do diretor ou do balanceador de carga de hardware que atendem a um pool de diretores.</p>
<p>O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</p></td>
<td><p>Este atributo representa o número da porta que deve ser usada para se conectar ao servidor que executa o serviço de borda de acesso.</p>
<p>O valor válido é um valor inteiro que especifica a porta a ser usada. O valor padrão é 5061.</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa o período de tempo limite da assinatura de presença padrão.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela do tempo limite de registro padrão.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela de tempo limite da assinatura de dados de roaming padrão.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Este atributo é usado em uma topologia de domínio dividido e contém um FQDN (nome de domínio totalmente qualificado).</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres UNICODE de valor único contém uma descrição amigável da rota de telefone ou da regra de normalização.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Este atributo representa um domínio configurado para o registrador.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Este atributo especifica o FQDN do servidor que executa o serviço de borda de acesso.</p>
<p>O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsoleto)</p></td>
<td><p>Este atributo controla se um servidor gera uma solicitação de notificação de melhor esforço (benotificar), em vez de uma solicitação de notificação, em resposta a uma solicitação de assinatura de um cliente. BENOTIFY é uma extensão de aumento de desempenho para o handshake de notificação de assinatura onde o servidor gera solicitações de notificação de atendimento, em vez de solicitações de notificação regulares. O benefício de desempenho é que uma solicitação de notificação de atendimento não requer uma resposta de 200 OK do cliente à medida que a solicitação de notificação faz.</p>
<p>Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</p>
<div>

> [!NOTE]  
> O Live Communications Server 2003 não dá suporte a solicitações de notificação de notificações. Para interoperar com aplicativos de servidor escritos com a API de servidor do Live Communications Server 2003 em execução no Live Communications Server 2005 e servidores de terceiros, as solicitações de notificações podem ser desabilitadas definindo seu valor como <STRONG>false</STRONG>. O benotification não faz parte do processo de padronização SIP do IETF (Internet Engineering Task Force).


</div></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsoleto)</p></td>
<td><p>Este atributo é uma opção global que os administradores de ti usam para configurar se os usuários têm permissão para se comunicar com os usuários de outras organizações. Permite que um administrador substitua o atributo <strong>FederationEnabled</strong> de um usuário individual. Esse atributo pode ser útil para ajudar a proteger a rede interna contra ataques da Internet que podem ser causados por worms, vírus ou ataques direcionados à empresa.</p>
<p>Os valores válidos (e as posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>1: habilitado para conectividade de IM pública (posição de bit 0)</p></li>
<li><p>2: reservado (posição de bit 1)</p></li>
<li><p>4: reservado (posição de bit 2)</p></li>
<li><p>8: reservado (posição de bit 3)</p></li>
<li><p>16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants is (permitir que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</p></li>
<li><p>128: UCEnabled (habilitar usuários para comunicações unificadas) (posição de bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posição de bit 9)</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Este atributo indica se os serviços corporativos são carregados em um determinado servidor.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Este atributo contém o código de discagem para acesso externo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Este atributo controla se um único usuário está habilitado para Federação. Ela é imposta pela camada de serviços corporativos. Ele está marcado para replicação do catálogo global.</p>
<p>Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Este atributo é uma lista de vários valores dos nomes de domínio de todos os servidores Enterprise Edition associados a um pool.</p>
<p>Vínculo inverso: <strong>link ID 11023</strong></p>
<p>O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-gateways (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres de valores múltiplos contém uma lista de gateways e portas (por gateway).</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsoleto)</p></td>
<td><p>Este atributo armazena nomes: pares de valores. O par nome já definido: valor é para a configuração <strong>permitir sondagem de presença</strong> .</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Groupingid</p></td>
<td><p>Este atributo é um identificador exclusivo de um grupo usado para agrupar entradas do catálogo de endereços.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2003 (não usado).</p>
<p>Obsoleto no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2003.</p>
<p>Obsoleto no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2003 (não usado).</p>
<p>Obsoleto no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Este atributo controla se um único usuário está habilitado para o acesso de usuário externo. Ela é imposta pela camada de serviços corporativos. Ele está marcado para replicação do catálogo global.</p>
<p>Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2003</p>
<p>Obsoleto no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>Linha msRTCSIP</p></td>
<td><p>Este atributo de valor único contém a ID do dispositivo (o URI do SIP ou o URI de TEL do telefone que os controles de usuário) usados pelo Lync para telefonia. Esse atributo é marcado para replicação de catálogo global e é indexado. Se um usuário estiver habilitado para o Enterprise Voice, este atributo armazenará a versão normalizada E. 164 do número de telefone do usuário.</p></td>
<td><p>Novo no Microsoft Office Live Communications Server 2005 com SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Este atributo de valor único contém o URI SIP do servidor de gateway CSTA-SIP. Este atributo está marcado para replicação de catálogo global, mas não está indexado.</p></td>
<td><p>Novo no Microsoft Office Live Communications Server 2005 com SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (obsoleto)</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (obsoleto)</p></td>
<td><p>Este atributo com valores múltiplos contém uma lista de nomes distintos de normalização (DN) locais associados a esse perfil de local. O tipo desse atributo é um binário DN. Há uma relação um-para-muitos entre o perfil de local e as regras de normalização local. A ordenação da lista de DNs de normalização local deve ser mantida na ordem especificada pelo administrador. A preservação do pedido é mantida pela parte binária do binário DN, que especifica o índice de pedidos.</p>
<p>Link encaminhar: <strong>link ID 11034</strong></p>
<p>O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Este atributo contém uma lista de opções para a regra de normalização.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (obsoleto)</p></td>
<td><p>Esse atributo de valor único contém um nome amigável para o perfil de local que indica qual local esse perfil representa. Como pode haver vários perfis de local, o administrador precisa de uma maneira de distinguir entre diferentes perfis.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsoleto)</p></td>
<td><p>Este atributo com valores múltiplos contém uma lista de nomes distintos do perfil de local. Este atributo especifica o vínculo inverso com um ou mais perfis de local.</p>
<p>Vínculo inverso: <strong>link ID 11035</strong></p>
<p>Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (obsoleto)</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Este atributo contém as opções para o perfil de local.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Este atributo de vários valores contém uma lista de contatos de aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Este atributo de vários valores contém uma lista de perfis de local.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</p></td>
<td><p>Este atributo representa o número máximo de solicitações de pesquisa pendentes por servidor.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</p></td>
<td><p>O atributo representa o número máximo de inscrições por usuário.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela de tempo limite máximo da assinatura.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela de tempo limite de registros máximos.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela de tempo limite máximo de assinaturas de dados móveis.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Este atributo é um atributo de ponto de controle de serviço na classe Computer que especifica um link de volta à fábrica da unidade de controle multiponto (MCU) à qual ele pertence. Esse atributo e o ponto de controle de serviço são criados para cada Microsoft MCU. Cada Microsoft MCU deve localizar o servidor back-end do pool ao qual ele pertence, para recuperar as configurações de nível de pool.</p>
<p>O valor desse atributo é o nome diferenciado (DN) da fábrica MCU. Este é um atributo de valor único e marcado para replicação de catálogo global.</p>
<p>Link encaminhar: <strong>link ID 11026</strong></p>
<p>O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Este é um atributo reservado de cadeia de caracteres múltipla. As configurações armazenadas nesse atributo são representadas como pares nome = valor. Os pares name = value atualmente definidos são:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Este é um atributo de valor único que contém o nome diferenciado (DN) de uma única fábrica de MCU associada a um pool.</p>
<p>Link encaminhar: <strong>link ID 11024</strong></p>
<p>O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Este atributo é uma cadeia de caracteres de valor único que especifica o GUID do provedor de fábrica MCU. Com base no valor de GUID, o processo de fábrica da MCU determina se deve ser atendido este tipo de MCU. Se o valor de GUID for <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, o processo de fábrica MCU (disponível por padrão no Lync Server) o processará. Para qualquer outro valor de GUID, o processo de fábrica MCU não irá atender ao tipo MCU.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Este atributo é uma lista de vários valores de nomes diferenciados (DN). Este atributo contém uma lista de todos os servidores MCU do mesmo tipo e fornecedor associados a essa fábrica de MCU. O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p>
<p>Vínculo inverso: link ID 11027</p>
<p>O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Este atributo é uma cadeia de caracteres de valor único que especifica o meio que o MCU pode lidar.</p>
<p>Os tipos válidos suportados são:</p>
<ul>
<li><p>Atenda</p></li>
<li><p>áudio-vídeo</p></li>
<li><p>chat</p></li>
<li><p>Phone-conf</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Este atributo é uma cadeia de caracteres de valor único que especifica o nome de um fornecedor MCU. Todos os Microsoft MCUs especificarão esse atributo como <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsoleto)</p></td>
<td><p>Este atributo define opções de reunião diferentes que são habilitadas globalmente para todos os usuários ou objetos de contato. Este atributo é um valor de máscara de bits de tipo inteiro.</p>
<p>Os valores válidos (e as posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants is é nenhum (não permitir que os usuários convidem usuários anônimos para reuniões) (nenhum bit definido)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants is é todos (permitir que todos os usuários convidem usuários anônimos para reuniões) (posição de bit 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants is é UsePerUserSetting (permitir que os usuários convidem usuários anônimos para reuniões com base na configuração do usuário) (posição de bit 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (a política de reunião é definida por usuário) (posição de bit 4)</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsoleto)</p></td>
<td><p>Este atributo especifica o nome diferenciado (DN) da política que o administrador atribuiu a este usuário como um atributo de valor único.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela de tempo limite de assinatura de presença mínima.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela do tempo limite mínimo de registro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Este atributo representa a janela de tempo limite de assinatura de dados de roaming mínimo.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de front-ends.</p></td>
<td><p>Novo no Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Este atributo contém opções e sinalizadores que definem as configurações de mobilidade.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Este atributo contém o DN de um objeto de política de mobilidade.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsoleto)</p></td>
<td><p>Este atributo representa o número permitido de dispositivos nos quais um usuário pode se registrar para comunicações SIP e inscrever-se em presença.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Este atributo especifica as opções que são habilitadas para o usuário ou objeto de contato. Este atributo é um valor de máscara de bits do tipo inteiro. Cada opção é representada por um bit. Este atributo está marcado para replicação de catálogo global.</p>
<p>Os valores válidos (e as posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>1: habilitado para conectividade de mensagens instantâneas públicas (IM) (posição de bit 0)</p></li>
<li><p>2: reservado (posição de bit 1)</p></li>
<li><p>4: reservado (posição de bit 2)</p></li>
<li><p>8: reservado (posição de bit 3)</p></li>
<li><p>16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants is (permitir que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</p></li>
<li><p>128: UCEnabled (habilitar usuários para UC) (posição de bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posição de bit 9)</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005 com SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Esse atributo é usado em topologias de floresta central e de recursos para habilitar o logon único quando o objeto userid da conta principal do Windows NT Server é copiado para este atributo do usuário ou do objeto de contato correspondente na floresta de recursos ou central. O Communicator Web Access pesquisa um usuário no AD DS usando este atributo ou o objeto userid. Este atributo está marcado para replicação de catálogo global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Este atributo é o nome de recurso uniforme (URN) do proprietário de um contato de aplicativo.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres de valor único contém um padrão usado para números de discagem correspondentes no formato E. 164. Se o número de discagem corresponder a este padrão, a tradução será aplicada ao número discado.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsoleto)</p></td>
<td><p>Este atributo com valores múltiplos contém uma lista de nomes distintos de rotas de telefone (DN). Este atributo especifica o vínculo inverso com uma ou mais rotas de telefone.</p>
<p>Vínculo inverso: <strong>link ID 11033</strong></p>
<p>Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (obsoleto)</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da rota de telefone, para que possa ser facilmente referenciado pelo administrador.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (obsoleto)</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (obsoleto)</p></td>
<td><p>Este atributo é uma cadeia de caracteres Unicode de valor único. Este atributo de cadeia de caracteres contém a definição de política no formato XML. A definição de esquema XML é comum entre diferentes tipos de política, apenas as configurações são diferentes para cada tipo de política.</p>
<p>A definição de esquema XML (XSD) é definida da seguinte maneira:</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (obsoleto)</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres Unicode de valor único contém o tipo de política. Os tipos de política válidos são os seguintes:</p>
<ul>
<li><p>Atenda</p></li>
<li><p>telefonia</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Este atributo especifica um link de volta para o pool ao qual um computador pertence. Esse atributo é definido independentemente se o computador está executando a edição Standard ou Enterprise Edition do Lync Server. Este atributo está marcado para replicação de catálogo global.</p>
<p>O valor válido é o nome de domínio do pool.</p>
<p>Link encaminhar: <strong>link ID 11022</strong></p>
<p>O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Este é um atributo com valores múltiplos que contém uma lista de nomes diferenciados (DN) de pools com os quais a fábrica MCU está associada.</p>
<p>Vínculo inverso: <strong>link ID 11025</strong></p>
<p>O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Live Communications Server 2005 com SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Este atributo especifica um nome arbitrário para um pool que é exibido pelo console de gerenciamento. Esse nome pode ser alterado pelo administrador.</p>
<p>O valor válido é uma cadeia de caracteres que representa o nome de um pool.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Este atributo é um valor de cadeia de caracteres de valor único. O valor desse atributo, quando presente, representa o FQDN do domínio do pool se o administrador quiser criar um pool de front-ends com um FQDN que não esteja de acordo com a estrutura de domínio do Active Directory na qual o pool de front-ends é criado (por exemplo, um SIP namespace desassociado do namespace DNS (sistema de nomes de domínio).</p>
<p>Recomendamos que você mapeie o FQDN do domínio do pool de front-ends para a parte do nome de domínio como o domínio do Active Directory no qual o pool reside. Portanto, quando nenhum valor estiver presente nesse atributo, o FQDN do pool de front-ends será o padrão para a estrutura de nome de domínio do Active Directory, conforme indicado pelo atributo <strong>dNSHostName</strong> .</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Uma lista de vários valores dos nomes de domínio de todos os servidores do Lync Server, Enterprise Edition associados a um pool. Este atributo do tipo Integer define se o pool é capaz de mensagens instantâneas (IM) e presença e reuniões.</p>
<p>Os tipos de valor válidos possíveis são os seguintes:</p>
<ul>
<li><p>Indefinido: serviço de mensagens instantâneas e presença (Live Communications Server 2005 e 2003)</p></li>
<li><p>1: serviço de mensagens instantâneas e presença (Lync Server)</p></li>
<li><p>2: mensagens instantâneas e serviços de presença e de reunião (Lync Server)</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pooltype</p></td>
<td><p>Este atributo especifica se um pool de servidores está executando o Standard Edition Server ou o servidor Enterprise Edition. Este atributo é um valor de máscara de bits do tipo inteiro. Cada opção é representada por um bit.</p>
<p>Os valores válidos (e as posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>1: servidor Standard Edition, hospeda usuários (posição de bit 0)</p></li>
<li><p>2: servidor Enterprise Edition, hospeda usuários (posição de bit 1)</p></li>
<li><p>4: servidor Standard Edition, hospeda aplicativos (posição de bit 2)</p></li>
<li><p>8: servidor Enterprise Edition, hospeda aplicativos (posição de bit 3)</p></li>
</ul>
<p>Como o Lync Server não dá suporte a pools que hospedam apenas aplicativos, os únicos valores válidos são os seguintes:</p>
<ul>
<li><p>5: servidor Standard Edition, hospeda usuários e aplicativos (posições de bit 0 e 2)</p></li>
<li><p>10: servidor Enterprise Edition, hospeda usuários e aplicativos (posições de bit 1 e 3)</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Este atributo define a versão do pool. É um tipo inteiro que é incrementado com cada lançamento de produto principal.</p>
<p>Os tipos de valor válidos possíveis são os seguintes:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 com SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 com SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Este atributo contém opções e sinalizadores que definem configurações de presença.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Este atributo contém o DN de um objeto de política de presença.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Este atributo habilita um usuário ou contato para mensagens SIP. Ela é adicionada à classe Contact porque na topologia de floresta central, os objetos de contato, não os objetos de usuário, estão habilitados para SIP.</p>
<p>O valor válido é o DN do servidor Standard Edition ou pool de front-ends Enterprise Edition onde um usuário está hospedado.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Este atributo contém o endereço SIP de um determinado usuário.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-privado</p></td>
<td><p>Este atributo contém a ID do dispositivo de linha privada.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-roteável</p></td>
<td><p>Este atributo é um atributo booliano usado para determinar se o Lync Server está autorizado a encaminhar para esse serviço usando seu endereço GRUU. Se esse valor for definido como <strong>true</strong>, o Lync Server estará autorizado a encaminhar para esse serviço. Se esse valor for definido como <strong>false</strong>, o Lync Server não está autorizado a encaminhar para esse serviço.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres UNICODE de valor único define um atributo que qualifica o uso de uma rota de telefone. A seleção de uma rota de telefone é determinada com base em dois elementos: o atributo de uso atribuído à rota de telefone e os atributos de uso de política permitidos do chamador. A primeira rota de telefone com um atributo de uso que corresponda ao uso permitido pelo chamador está selecionada.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsoleto)</p></td>
<td><p>Este atributo de nome diferenciado (DN) com valores múltiplos contém uma lista de nomes diferenciados de uso de rota.</p>
<p>Link encaminhar: <strong>link ID 11032</strong></p>
<p>Este atributo é um link de encaminhamento para o vínculo inverso correspondente <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Este atributo contém o DN que aponta para o pool que todo o tráfego SIP endereçado a essa MCU ou serviço confiável deve passar.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da regra de normalização, para que possa ser facilmente referenciado por um administrador.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Este atributo representa a versão do esquema atualmente implantada na organização.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsoleto)</p></td>
<td><p>Este atributo limita o número de resultados de pesquisa a serem retornados de uma pesquisa de diretório quando um usuário procura um contato usando o Communicator. Este atributo substituirá o valor fornecido pelo cliente.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsoleto)</p></td>
<td><p>Esse atributo limita o número de solicitações de pesquisa retornadas.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Esse atributo com valores múltiplos é um vínculo inverso que contém uma lista de nomes diferenciados (DN). Esse DNs aponta para um objeto pool ou <strong>TrustedService</strong> .</p>
<p>Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Serverrestauração</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsoleto)</p></td>
<td><p>Este atributo com valores múltiplos contém uma lista de nomes distintos. Esses nomes distintos são links de volta que fazem referência a outros objetos de servidor que podem ser atribuídos a um perfil de local padrão.</p>
<p>Vínculo inverso: <strong>link ID 11037</strong></p>
<p>O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Este atributo de vínculo inverso faz referência somente a pools e servidores de mediação.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Este atributo define as informações de versão do servidor. Este número de versão se aplica a todas as funções de servidor. É um número inteiro de monotonously que aumenta com o lançamento de cada produto oficial.</p>
<p>Os valores válidos possíveis são os seguintes:</p>
<ul>
<li><p>Indefinido: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 with SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Este atributo de valor único de tipo inteiro especifica o tipo de objeto ao qual o <strong>msDS-SourceObjectDN</strong> aponta, da seguinte maneira:</p>
<ul>
<li><p>nulo | 0x00000001: representa um objeto de usuário principal do Windows NT Server de uma floresta diferente</p></li>
<li><p>Os atributos a seguir representam um tipo de grupo de uma floresta diferente para expansão de grupo de distribuição:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: representa um objeto de atendedor automático ou de acesso de assinante da mesma floresta ou de uma floresta diferente</p></li>
</ul></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2003.</p>
<p>Obsoleto no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Este atributo permite mover um objeto de usuário ou de contato de um pool do Lync Server para outro. Esse atributo é adicionado à classe Contact, porque na topologia de floresta central, os objetos de contato, não os objetos de usuário, estão habilitados para SIP.</p>
<p>O valor válido é o DN do servidor Standard Edition ou pool de front-ends para o qual o usuário deve ser movido.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres de valor único contém um padrão ou intervalo de números de telefone para rotear para os gateways especificados em <strong>msRTCSIP-gateways</strong>.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Este atributo armazena pares nome-valor para políticas de destino para usuários do Lync Server.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Tenantid</p></td>
<td><p>Este atributo armazena o identificador exclusivo de um locatário.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (obsoleto)</p></td>
<td><p>Este atributo é usado pelo recurso de voz do Lync Server e contém a cadeia de caracteres de conversão a ser aplicada no número discado, se uma correspondência for encontrada.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Este atributo é um valor String que contém o FQDN do MCU. Este é um atributo de valor único. O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Este atributo é um valor String que contém o FQDN do servidor de proxy em execução. Este atributo tem valor único. O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Este atributo é um atributo de valor único que representa o FQDN de um servidor confiável.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Este atributo especifica o número de versão de um servidor na lista de servidores confiáveis.</p>
<p>Os valores válidos possíveis são os seguintes:</p>
<ul>
<li><p>NULO: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Este atributo define as opções que são habilitadas para o serviço confiável.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Este atributo com valores múltiplos contém uma lista de nomes diferenciados (DN) que fazem referência a um objeto de serviço confiável, como um serviço de autenticação de retransmissão de mídia. Um serviço de autenticação de retransmissão de mídia (colocado fisicamente no servidor de borda executando o serviço de conferência A/V) deve estar associado a um pool para dar suporte a cenários de áudio para usuários remotos.</p>
<p>O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Este atributo é um número inteiro que define o número da porta usada para se conectar ao serviço GRUU.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Este atributo é um valor String que define o tipo de serviço GRUU que ele representa.</p>
<p>Os tipos de serviço válidos do GRUU são os seguintes:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Gateway</p></li>
<li><p>Serviço de autenticação de retransmissão de mídia (MRAS)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-userextension CWA</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Este atributo é um valor String que contém o FQDN do IIS que executa os serviços Web do Lync Server. Este é um atributo de valor único. O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsoleto)</p></td>
<td><p>Este atributo define opções de UC diferentes que são habilitadas globalmente para todos os objetos de contato ou usuário. Este atributo é um valor de máscara de bits de tipo inteiro. Cada opção é representada pela presença de um bit.</p>
<p>O valor válido possível (e a posição de bit associada) são os seguintes:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (posição de bit 2)</p></li>
</ul>
<p>Quando esse bit é definido, a política de UC é definida por usuário.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsoleto)</p></td>
<td><p>Este atributo de valor único contém o nome diferenciado (DN) da política de UC que o administrador atribuiu para este usuário.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-userdomainlist (obsoleto)</p></td>
<td><p>Este atributo fornece uma lista de todos os domínios em uma floresta que hospedam usuários habilitados para SIP. O padrão é uma lista vazia, indicando que todos os domínios na floresta são habilitados para SIP.</p>
<p>Os valores válidos são várias cadeias de caracteres que representam os nomes de domínio de domínios individuais.</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-userhabilitado</p></td>
<td><p>Este atributo determina se o usuário está atualmente habilitado para o Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-userextension</p></td>
<td><p>Este atributo com valores múltiplos contém uma lista de pares nome-valor no formato de &quot;nome = valor. &quot; Este atributo está marcado para replicação de catálogo global.</p></td>
<td><p>Novo no Live Communications Server 2005 com SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Este atributo contém o nome diferenciado (DN) que aponta para um objeto de perfil de local.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-userpolicies</p></td>
<td><p>Este atributo armazena pares nome-valor para políticas de usuário.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Este é um atributo com valores múltiplos contendo uma lista de nomes distintos com binário (DN_WITH_BINARY) apontando para políticas de usuário global de tipos diferentes. A parte binária indica o tipo de política para o qual a parte DN aponta.</p>
<p>Os valores binários válidos são os seguintes:</p>
<ul>
<li><p>0x00000001: política de reunião</p></li>
<li><p>0x00000002: política de UC</p></li>
<li><p>0x00000005: política de presença</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.</p></td>
<td><p>Novo no Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Este é um atributo com vários valores. Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Esse atributo de valor único aponta para o pool ou servidor Standard Edition ao qual os componentes Web pertencem.</p>
<p>Link encaminhar: <strong>link ID 11028</strong></p>
<p>O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Este atributo é uma lista de vários valores de nomes distintos. Este atributo contém uma lista de todos os servidores Web associados a esse pool.</p>
<p>Vínculo inverso: <strong>link ID 11029</strong></p>
<p>O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novo no Live Communications Server 2003.</p>
<p>Obsoleto no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Esse atributo existente do Active Directory é usado por telefonia para especificar a lista de endereços TCP/IP alternativos de um telefone.</p></td>
<td><p>Novo no sistema operacional Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Este atributo existente do Active Directory é usado pelos componentes de voz no Lync Server, apenas para objetos de contato, para fins de roteamento de chamadas para o atendedor automático da Unificação de mensagens e os números de acesso do Assinante. O endereço de encaminhamento de chamadas não condicional é armazenado nesse atributo com valores múltiplos. Essa conta é criada para a finalidade específica do atendedor automático e acesso ao Assinante. Os atributos da conta não devem ser modificados pelos administradores.</p></td>
<td><p>Novo no sistema operacional Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Este atributo de múltiplos valores do Active Directory existente é parte do esquema base do Active Directory introduzido no Windows 2000. Este atributo contém os vários endereços X400, X500 e SMTP do email do usuário. No Live Communications Server 2003 e posterior, o URI do SIP do usuário é adicionado a essa lista, &quot;usando a&quot; marca SIP:.</p>
<p>Os seguintes aplicativos pesquisam o URI do SIP do usuário a partir deste atributo:</p>
<ul>
<li><p>Cliente de mensagens e colaboração do Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Novo no sistema operacional Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Este atributo existente do Active Directory contém o número de telefone do usuário.</p></td>
<td><p>Novo no sistema operacional Windows 2000.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

