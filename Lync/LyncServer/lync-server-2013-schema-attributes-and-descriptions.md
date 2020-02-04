---
title: 'Lync Server 2013: atributos e descrições do esquema'
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
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Atributos e descrições de esquema no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

Esta seção descreve todos os atributos de esquema usados pelo Lync Server 2013. Para as classes associadas a atributos, consulte [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Para obter uma lista de classes e atributos que são novos no Lync Server 2013, consulte [mudanças de esquema no Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Os atributos que são pares vinculados são especificados como links de encaminhamento ou links para trás. Um atributo que faz referência a outro objeto é um link de encaminhamento; o atributo do outro objeto que faz referência novamente ao primeiro objeto é um link para trás. Os links de encaminhamento são atualizáveis, enquanto links de volta são somente leitura.

Alguns atributos têm um valor de máscara de bits. Para esses atributos, cada configuração é representada por um bit, e o valor decimal exibido representa a posição do bit. Posições de bit começam com bit 0. Por exemplo, 1 (binário) é bit 0 definido e 10000 (binário) é um bit 4 definido. Cada bit representa uma propriedade. Veja a seguir alguns exemplos:

  - 10000 (binário) tem um valor decimal de 16 (ou seja, bit 4 é definido).

  - 100 milhões (binário) tem um valor decimal de 256 (ou seja, o bit 8 é definido).

  - 1100 (binário) tem um valor decimal de 12 (ou seja, os bits 2 e 3 são definidos; as propriedades representadas por ambos os bits são habilitadas).

  - 1111000001 (binário) tem um valor decimal de 961 (ou seja, bits 0, 6, 7, 8 e 9 são definidos; as propriedades de cada um desses bits são habilitadas).

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Atributos de esquema do Lync Server 2013

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
<td><p>Atributos</p></td>
<td><p>Um atributo existente nos serviços de domínio Active Directory que agora está associado às classes <strong>msRTCSIP-pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> . Esse atributo especifica o nome de domínio totalmente qualificado (FQDN) de um pool ou um servidor de monitoramento.</p>
<p>Um valor válido para cada segmento é de 63 caracteres; um valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Esse atributo contém a representação de cadeia de caracteres do nome diferenciado (DN) do objeto em outra floresta que corresponde a esse objeto. Esse atributo é usado para expansão do grupo de distribuição e atendimento automático. Esse atributo é definido no esquema padrão do Active Directory para Windows Server 2003 R2.</p>
<p>Para evitar a necessidade de uma atualização do AD DS para o Windows Server 2003 R2, a preparação do esquema do Active Directory estende o esquema do Windows Server 2003 com essa definição de atributo.</p></td>
<td><p>Novo no Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Esse atributo com vários valores contém as configurações da caixa postal. Esse atributo é compartilhado com o Exchange Unified Messaging (UM).</p></td>
<td><p>Novo no Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Esse atributo de vários valores contém identificadores para políticas de retenção que se aplicam ao usuário. As políticas de retenção preservam os itens da caixa de correio para o usuário durante o período de espera. Esse atributo é compartilhado com o Exchange 2013.</p></td>
<td><p>Novo no Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Esse atributo armazena informações do provedor de audioconferência de áudio para um usuário.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Esse atributo aponta para a entrada de serviço confiável do contato do aplicativo.</p></td>
<td><p>Novo no Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Aplicativolist</p></td>
<td><p>Esse atributo contém uma lista de aplicativos hospedados no servidor de aplicativos.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP – ApplicationOptions</p></td>
<td><p>Esse atributo especifica as opções para o contato do aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Esse atributo contém o idioma principal para o contato do aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Esse atributo Multiple Value contém os idiomas secundários para o contato do aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Esse atributo contém uma lista de servidores de aplicativos que pertencem a este pool. O link encaminhamento correspondente a este atributo de link regressivo é <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Esse atributo aponta para o pool ao qual esse servidor de aplicativos pertence. Este é o link encaminhar. O link regressivo correspondente é <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
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
<td><p>Esse atributo especifica o padrão global dentro do limite da floresta para arquivar todas as comunicações do usuário. Isso é imposto pela camada do agente de arquivamento. O intervalo de valores para esse atributo é o seguinte:</p>
<ul>
<li><p><strong>True</strong>: arquivar todos os usuários</p></li>
<li><p><strong>False</strong>: Não arquivar todos os usuários</p></li>
</ul>
<p>Esse atributo controla globalmente, dentro do limite da floresta, como as comunicações do usuário em uma rede interna são arquivadas.</p>
<p><strong>Comportamento do Live Communications Server 2005 (agora desativado)</strong></p>
<p>O intervalo de valores para esse atributo é o seguinte:</p>
<ul>
<li><p>0: arquivar o corpo da mensagem [bit 0]</p></li>
<li><p>1: Não arquivar o corpo da mensagem [bit 0]</p></li>
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
<td><p>Esse atributo é um inteiro usado como um campo de bits para controlar se as comunicações de um único usuário devem ser arquivadas. Esse controle é imposto pela camada do agente de arquivamento. Ele está marcado para replicação de catálogo global.</p>
<p>O escopo desse atributo é específico para um único usuário ou contato. Os valores válidos (e posições de bit associadas) do Lync Server são os seguintes:</p>
<ul>
<li><p>0: Não arquivar (nenhum conjunto de bits)</p></li>
<li><p>1: desativado (posição do bit 0)</p></li>
<li><p>2: desativado (posição do bit 1)</p></li>
<li><p>4: Arquivar comunicações internas (posição do bit 2)</p></li>
<li><p>8: Arquivar comunicações federadas (posição de bit 3)</p></li>
</ul>
<p>Os valores válidos anteriormente no Live Communications Server 2005 são os seguintes:</p>
<ul>
<li><p>0: Use o valor padrão definido por <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation</strong> nesta ordem de precedência:</p>
<ul>
<li><p>1: arquivo morto</p></li>
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
<td><p>Esse atributo define a versão do serviço de arquivamento. Esse atributo é um tipo de inteiro que aumenta o monotonously que aumenta com cada lançamento oficial do produto. Os valores válidos possíveis são:</p>
<ul>
<li><p>Indefinido: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 com SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Esse atributo especifica o FQDN do servidor back-end do pool. Como só pode haver um único servidor back-end por pool, esse é um atributo de valor único.</p>
<p>O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Esse atributo contém o identificador do pool que hospeda o diretório de conferências.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Esse atributo contém o identificador de um diretório de conferências.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Esse atributo contém o identificador do pool ao qual o diretório de conferências está sendo movido.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-padrão</p></td>
<td><p>Esse atributo booliano define se o uso do telefone é um uso padrão. Se esse atributo estiver definido como <strong>true</strong>, o uso do telefone será um uso padrão e não poderá ser excluído pelo administrador. Se esse atributo estiver definido como <strong>false</strong>, o uso poderá ser excluído.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Esse atributo identifica a URL do Communicator Web Access para usuários que estão fora da organização.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Esse atributo identifica a URL do Communicator Web Access para os usuários que estão dentro da organização.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsoleto)</p></td>
<td><p>Esse atributo com valor único contém o nome diferenciado (DN) de um objeto de classe de perfil de localização atribuído a ele.</p>
<p>Link encaminhar: <strong>ID do link 11036</strong></p>
<p>O link regressivo correspondente é <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsoleto)</p></td>
<td><p>Esse atributo booliano especifica se a política é uma política padrão. A política é uma política padrão quando definida como <strong>true</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</p></td>
<td><p>Esse atributo especifica o FQDN do servidor de borda que executa o serviço de borda de acesso, se ele puder ser acessado diretamente ou do balanceador de carga de hardware para um pool de servidores que executam o serviço de borda de acesso. Se os servidores que executam o serviço de borda de acesso só puderem ser acessados por meio de um ou mais directors, esse atributo especificará o FQDN e, opcionalmente, o número da porta do diretor ou do balanceador de carga de hardware que serve um pool de directors.</p>
<p>O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</p></td>
<td><p>Esse atributo representa o número da porta que deve ser usado para conexão com o serviço de borda de acesso do servidor que está executando.</p>
<p>O valor válido é um valor inteiro que especifica a porta a ser usada. O valor padrão é 5061.</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa o período de tempo limite da assinatura de presença padrão.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite de registro padrão.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite de assinatura de dados de roaming padrão.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Esse atributo é usado em uma topologia de domínio dividido e contém um FQDN (nome de domínio totalmente qualificado).</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Descrição (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres UNICODE com valor único contém uma descrição amigável da regra de normalização ou rota telefônica.</p></td>
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
<td><p>Esse atributo representa um domínio configurado para o registrador.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Esse atributo especifica o FQDN do serviço de borda de acesso do servidor que está executando.</p>
<p>O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsoleto)</p></td>
<td><p>Esse atributo controla se um servidor gera uma solicitação de notificação de melhor esforço (enviar notificação), em vez de uma solicitação de notificação, em resposta a uma solicitação de assinatura de um cliente. Mynotify é uma extensão de aprimoramento do desempenho para o handshake de notificação de assinatura em que o servidor gera solicitações de notificação de notificação, em vez de solicitações regulares de notificação. O benefício do desempenho é que uma solicitação de notificação não requer uma resposta de 200 OK do cliente, pois a solicitação de notificação faz.</p>
<p>Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</p>
<div>

> [!NOTE]  
> O Live Communications Server 2003 não oferece suporte a solicitações de notificação de notificação. Para interoperar com os aplicativos do servidor escritos com a API do servidor do Live Communications Server 2003 em execução no Live Communications Server 2005 e em servidores de terceiros, as solicitações de notificação podem ser desabilitadas definindo seu valor como <STRONG>false</STRONG>. Mynotify não faz parte do processo de padronização SIP do IETF (Internet Engineering Task Force).


</div></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsoleto)</p></td>
<td><p>Esse atributo é uma opção global que os administradores de ti usam para configurar se os usuários têm permissão para se comunicar com usuários de outras organizações. Ele permite que um administrador substitua o atributo <strong>FederationEnabled</strong> de um usuário individual. Esse atributo pode ser útil para ajudar a proteger a rede interna de ataques pela Internet que podem ser causados por worms, vírus ou ataques direcionados à empresa.</p>
<p>Os valores válidos (e posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>1: habilitado para conectividade de IM pública (posição do bit 0)</p></li>
<li><p>2: reservado (posição do bit 1)</p></li>
<li><p>4: reservado (posição do bit 2)</p></li>
<li><p>8: reservado (posição do bit 3)</p></li>
<li><p>16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permite que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</p></li>
<li><p>128: UCEnabled (habilitar usuários para comunicação unificada) (posição de bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posição do bit 9)</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Esse atributo indica se os serviços corporativos são carregados em determinado servidor.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Esse atributo contém o código de discagem para acesso externo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Esse atributo controla se um único usuário está habilitado para Federação. Ela é imposta pela camada de serviços corporativos. Ele está marcado para replicação de catálogo global.</p>
<p>Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Esse atributo é uma lista de vários valores dos nomes de domínio de todos os servidores Enterprise Edition associados a um pool.</p>
<p>Link para trás: <strong>ID do link 11023</strong></p>
<p>O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-gateways (obsoletos)</p></td>
<td><p>Este atributo de cadeia de caracteres de múltiplos valores contém uma lista de gateways e portas (por gateway).</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsoleto)</p></td>
<td><p>Esse atributo armazena nomes de valor: pares de valores. O par de nomes já definido: é para a configuração <strong>permitir sondagem para presença</strong> .</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Groupingid</p></td>
<td><p>Esse atributo é um identificador exclusivo de um grupo usado para agrupar entradas do catálogo de endereços.</p></td>
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
<td><p>Esse atributo controla se um único usuário está habilitado para o acesso de usuário externo. Ela é imposta pela camada de serviços corporativos. Ele está marcado para replicação de catálogo global.</p>
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
<td><p>Linha de msRTCSIP</p></td>
<td><p>Esse atributo com valor único contém a ID do dispositivo (o URI SIP ou o URI do TEL do telefone que o usuário controla) usado pelo Lync para telefonia. Esse atributo está marcado para replicação de catálogo global e está indexado. Se um usuário estiver habilitado para o Enterprise Voice, esse atributo armazenará a versão normalizada E. 164 do número de telefone do usuário.</p></td>
<td><p>Novo no Microsoft Office Live Communications Server 2005 com SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Esse atributo com valor único contém o URI SIP do servidor do gateway CSTA-SIP. Esse atributo está marcado para replicação de catálogo global, mas não está indexado.</p></td>
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
<td><p>Este atributo de valores múltiplos contém uma lista de nomes diferenciais de normalização (DN) locais associados a este perfil de local. O tipo desse atributo é um binário DN. Há uma relação um-para-muitos entre o perfil de local e as regras de normalização locais. A ordenação da lista de DNs de normalização local deve ser mantida na ordem especificada pelo administrador. A preservação do pedido é mantida pela parte binária do binário DN, que especifica o índice do pedido.</p>
<p>Link encaminhar: <strong>ID do link 11034</strong></p>
<p>O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-LocationProfileBL</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Esse atributo contém uma lista de opções para a regra de normalização.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (obsoleto)</p></td>
<td><p>Esse atributo com valor único contém um nome amigável para o perfil de local que indica qual local esse perfil representa. Como pode haver vários perfis de localização, o administrador precisa de uma maneira de distinguir entre diferentes perfis.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsoleto)</p></td>
<td><p>Esse atributo com valores múltiplos contém uma lista de nomes distintos do perfil de local. Esse atributo especifica o link back para um ou mais perfis de local.</p>
<p>Link para trás: <strong>ID do link 11035</strong></p>
<p>Esse atributo corresponde ao link Forward <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
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
<td><p>Esse atributo contém as opções do perfil de local.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Este atributo de vários valores contém uma lista de contatos do aplicativo.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Esse atributo de vários valores contém uma lista de perfis de localização.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</p></td>
<td><p>Esse atributo representa o número máximo de solicitações de pesquisa pendentes por servidor.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</p></td>
<td><p>O atributo representa o número máximo de assinaturas por usuário.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite máximo da assinatura.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite de registros máximos.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite de máximo de assinaturas de roaming de dados.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Esse atributo é um atributo de ponto de controle de serviço na classe Computer que especifica um link de volta para a fábrica da unidade de controle multiponto (MCU) à qual ele pertence. Esse atributo e este ponto de controle de serviço é criado para cada Microsoft MCU. Cada Microsoft MCU deve encontrar o servidor back-end do pool ao qual ele pertence, para recuperar as configurações no nível do pool.</p>
<p>O valor desse atributo é o nome diferenciado (DN) da fábrica do MCU. Esse é um atributo de valor único e marcado para replicação de catálogo global.</p>
<p>Link encaminhar: <strong>ID do link 11026</strong></p>
<p>O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Este é um atributo reservado de várias cadeias de caracteres. As configurações armazenadas nesse atributo são representadas como pares nome = valor. Pares nome = valor atualmente definidos são:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Esse é um atributo de valor único que contém o nome diferenciado (DN) de uma única fábrica de MCU associada a um pool.</p>
<p>Link encaminhar: <strong>ID do link 11024</strong></p>
<p>O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Esse atributo é uma cadeia de caracteres com valor único que especifica o GUID do provedor de fábrica MCU. Com base no valor GUID, o processo de fábrica do MCU determina se o tipo de MCU deve ser atendido. Se o valor GUID for <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, o processo de fábrica do MCU (disponível por padrão no Lync Server) o processará. Para qualquer outro valor de GUID, o processo de fábrica da MCU não irá atender ao tipo de MCU.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Esse atributo é uma lista com vários valores de nomes diferenciados (DN). Esse atributo contém uma lista de todos os servidores MCU do mesmo tipo e fornecedor associados a essa fábrica de MCU. O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p>
<p>Link para trás: ID do link 11027</p>
<p>O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Esse atributo é uma cadeia de caracteres com valor único que especifica a mídia que a MCU pode manipular.</p>
<p>Os tipos válidos com suporte são:</p>
<ul>
<li><p>reunião</p></li>
<li><p>áudio-vídeo</p></li>
<li><p>chat</p></li>
<li><p>telefone-conf</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Esse atributo é uma cadeia de caracteres de valor único que especifica o nome de um fornecedor de MCU. Todos os Microsoft MCUs especificarão esse atributo para ser <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsoleto)</p></td>
<td><p>Esse atributo define diferentes opções de reunião que são habilitadas globalmente para todos os usuários ou objetos de contato. Esse atributo é um valor de máscara de bits do tipo inteiro.</p>
<p>Os valores válidos (e posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants é nenhum (não permitir que os usuários convidem usuários anônimos para reuniões) (nenhum bit definido)</p></li>
<li><p>4: o AllowOrganizeMeetingWithAnonymousParticipants é todos (permitir que todos os usuários convidem usuários anônimos para reuniões) (posição do bit 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants é UsePerUserSetting (permitir que os usuários convidem usuários anônimos para reuniões com base na configuração por usuário) (posição de bit 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (a política de reunião é definida por usuário) (posição 4 do bit)</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsoleto)</p></td>
<td><p>Esse atributo especifica o nome diferenciado (DN) da política que o administrador atribuiu para este usuário como um atributo de valor único.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite de assinatura de presença mínima.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite de inscrição mínima.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Esse atributo representa a janela de tempo limite de assinatura de dados de roaming mínimo.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Esse atributo é usado para armazenar o back-end do SQL Server espelhado usado pelo pool de front-ends.</p></td>
<td><p>Novo no Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Esse atributo contém opções e sinalizadores que definem as configurações de mobilidade.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Esse atributo contém o DN para um objeto de política de mobilidade.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsoleto)</p></td>
<td><p>Esse atributo representa o número permitido de dispositivos nos quais um usuário pode se registrar para comunicações SIP e se inscrever na presença.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Esse atributo especifica as opções que são habilitadas para o objeto de contato ou usuário. Esse atributo é um valor de máscara de bits do tipo inteiro. Cada opção é representada por um pouco. Esse atributo está marcado para replicação de catálogo global.</p>
<p>Os valores válidos (e posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>1: habilitado para conectividade de mensagens instantâneas (IM) públicas (posição do bit 0)</p></li>
<li><p>2: reservado (posição do bit 1)</p></li>
<li><p>4: reservado (posição do bit 2)</p></li>
<li><p>8: reservado (posição do bit 3)</p></li>
<li><p>16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (permite que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</p></li>
<li><p>128: UCEnabled (habilitar usuários para UC) (posição do bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posição do bit 9)</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005 com SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Esse atributo é usado em topologias de floresta central e de recursos para habilitar o logon único quando os objetos do usuário da conta principal do Windows NT Server são copiados para esse atributo do usuário ou do objeto de contato correspondente no recurso ou na floresta central. O Communicator Web Access procura por um usuário no AD DS usando esse atributo ou o ObjectID do usuário. Esse atributo está marcado para replicação de catálogo global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Esse atributo é o nome de recurso uniforme (URN) do proprietário de um contato de aplicativo.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-padrão (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres de valor único contém um padrão usado para números de discagem correspondentes no formato E. 164. Se o número de discagem coincidir com esse padrão, a tradução será aplicada ao número discado.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsoleto)</p></td>
<td><p>Este atributo de valores múltiplos contém uma lista de nomes distintos de rota de telefone (DN). Esse atributo especifica o link para trás para uma ou mais rotas de telefone.</p>
<p>Link para trás: <strong>ID do link 11033</strong></p>
<p>Esse atributo corresponde ao link Forward <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
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
<td><p>Esse atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da rota do telefone, para que ele possa ser referenciado facilmente pelo administrador.</p></td>
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
<td><p>Esse atributo é uma cadeia de caracteres Unicode com um único valor. Este atributo de cadeia de caracteres contém a definição de política no formato XML. A definição do esquema XML é comum em diferentes tipos de política, apenas as configurações são diferentes para cada tipo de política.</p>
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
<td><p>Esse atributo de cadeia de caracteres Unicode com valor único contém o tipo de política. Os tipos de política válidos são os seguintes:</p>
<ul>
<li><p>reunião</p></li>
<li><p>telefonia</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Esse atributo especifica um link de volta para o pool ao qual um computador pertence. Esse atributo é definido independentemente de o computador estar executando a edição Standard ou Enterprise do Lync Server. Esse atributo está marcado para replicação de catálogo global.</p>
<p>O valor válido é o nome de domínio do pool.</p>
<p>Link encaminhar: <strong>ID do link 11022</strong></p>
<p>O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Esse é um atributo de valores múltiplos que contém uma lista de nomes diferenciados (DN) de pools com os quais a fábrica do MCU está associada.</p>
<p>Link para trás: <strong>ID do link 11025</strong></p>
<p>O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Live Communications Server 2005 com SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Esse atributo especifica um nome arbitrário para um pool que é exibido pelo console de gerenciamento. Esse nome pode ser alterado pelo administrador.</p>
<p>O valor válido é uma cadeia de caracteres que representa o nome de um pool.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Esse atributo é um valor de cadeia de caracteres de valor único. O valor desse atributo, quando presente, representa o FQDN do domínio do pool se o administrador quiser criar um pool de front-end com um FQDN que não esteja em conformidade com a estrutura de domínio do Active Directory na qual o pool de front-ends é criado (por exemplo, um SIP namespace desincluído do namespace DNS (sistema de nomes de domínio)).</p>
<p>Recomendamos que você mapeie o FQDN do domínio do pool de front-end para a parte do nome do domínio como o domínio do Active Directory no qual o pool reside. Portanto, quando nenhum valor estiver presente nesse atributo, o FQDN do pool de front-end usará como padrão a estrutura de nomes de domínio do Active Directory, como indicado pelo atributo <strong>dNSHostName</strong> .</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Uma lista de vários valores de todos os nomes de domínio de todos os servidores do Lync Server, Enterprise Edition associados a um pool. Esse atributo do tipo Integer define se o pool é capaz de enviar mensagens instantâneas (IM) e presença e reuniões.</p>
<p>Os possíveis tipos de valor válidos são os seguintes:</p>
<ul>
<li><p>Indefinido: serviço de mensagem instantânea e de presença (Live Communications Server 2005 e 2003)</p></li>
<li><p>1: serviço de mensagem instantânea e de presença (Lync Server)</p></li>
<li><p>2: mensagens de chat e presença e serviço de reunião (Lync Server)</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pooltype</p></td>
<td><p>Esse atributo especifica se um pool de servidores está executando o Standard Edition Server ou o Enterprise Edition Server. Esse atributo é um valor de máscara de bits do tipo inteiro. Cada opção é representada por um pouco.</p>
<p>Os valores válidos (e posições de bit associadas) são os seguintes:</p>
<ul>
<li><p>1: servidor de edição padrão, usuários de host (posição do bit 0)</p></li>
<li><p>2: Enterprise Edition Server, usuários de host (posição de bit 1)</p></li>
<li><p>4: servidor Standard Edition, aplicativos de host (posição 2 do bit)</p></li>
<li><p>8: Enterprise Edition Server, aplicativos de host (posição de bit 3)</p></li>
</ul>
<p>Como o Lync Server não oferece suporte a pools que hospedam apenas aplicativos, os únicos valores válidos são os seguintes:</p>
<ul>
<li><p>5: servidor Standard Edition, hospeda usuários e aplicativos (posições de bit 0 e 2)</p></li>
<li><p>10: Enterprise Edition Server, hospeda usuários e aplicativos (posições de bit 1 e 3)</p></li>
</ul></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Esse atributo define a versão do pool. É um tipo de inteiro que é incrementado com cada lançamento de produto principal.</p>
<p>Os possíveis tipos de valor válidos são os seguintes:</p>
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
<td><p>Esse atributo contém opções e sinalizadores que definem as configurações de presença.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Esse atributo contém o DN para um objeto de política de presença.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Esse atributo habilita um usuário ou contato para mensagens SIP. Ele é adicionado à classe Contact porque, na topologia de floresta central, objetos de contato, não objetos de usuário, estão habilitados para SIP.</p>
<p>O valor válido é o DN do servidor Standard Edition ou do pool Front-end da edição Enterprise onde um usuário é hospedado.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Esse atributo contém o endereço SIP de um determinado usuário.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-privado</p></td>
<td><p>Esse atributo contém a ID do dispositivo de linha particular.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-roteável</p></td>
<td><p>Esse atributo é um atributo booliano usado para determinar se o Lync Server está autorizado a direcionar para esse serviço usando seu endereço GRUU. Se esse valor for definido como <strong>true</strong>, o Lync Server estará autorizado a direcionar para esse serviço. Se esse valor for definido como <strong>false</strong>, o Lync Server não será autorizado a encaminhar para esse serviço.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres UNICODE com valor único define um atributo que qualifica o uso de uma rota telefônica. A seleção de uma rota telefônica é determinada com base em dois elementos: o atributo Usage atribuído à rota do telefone e os atributos de uso da política permitidos do chamador. A primeira rota telefônica com um atributo Usage que corresponda ao uso permitido pelo chamador está selecionada.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsoleto)</p></td>
<td><p>Este atributo de nome diferenciado (DN) contém uma lista de nomes diferenciados de uso de rota.</p>
<p>Link encaminhar: <strong>ID do link 11032</strong></p>
<p>Esse atributo é um link de encaminhamento para o link regressivo correspondente <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Esse atributo contém o DN que aponta para o pool que todo o tráfego SIP endereçado a essa MCU ou serviço confiável deve passar.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsoleto)</p></td>
<td><p>Esse atributo de cadeia de caracteres UNICODE com valor único especifica o nome amigável da regra de normalização para que possa ser referenciado facilmente por um administrador.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Esse atributo representa a versão do esquema atualmente implantada na organização.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsoleto)</p></td>
<td><p>Esse atributo limita o número de resultados da pesquisa a ser retornado de uma pesquisa de diretório quando um usuário pesquisa um contato usando o Communicator. Esse atributo irá substituir o valor fornecido pelo cliente.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsoleto)</p></td>
<td><p>Esse atributo limita o número de solicitações de pesquisa retornadas.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Este atributo de valores múltiplos é um link regressivo que contém uma lista de nomes diferenciados (DN). Este DNs aponta para um objeto de pool ou <strong>TrustedService</strong> .</p>
<p>Esse atributo corresponde ao link Forward <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsoleto)</p></td>
<td><p>Esse atributo de valores múltiplos contém uma lista de nomes distintos. Esses nomes diferenciados são links de volta que fazem referência a outros objetos do servidor que podem ser atribuídos a um perfil de local padrão.</p>
<p>Link para trás: <strong>ID do link 11037</strong></p>
<p>O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Este atributo back link faz referência a pools e somente servidores de mediação.</p></td>
<td><p>Novo no Office Communications Server 2007.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Esse atributo define as informações sobre a versão do servidor. Este número de versão se aplica a todas as funções de servidor. É um número inteiro monotonously que aumenta em incrementos com cada lançamento oficial do produto.</p>
<p>Os valores válidos possíveis são os seguintes:</p>
<ul>
<li><p>Indefinido: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 com SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>Esse atributo de valor único de tipo inteiro especifica o tipo de objeto ao qual o <strong>msDS-SourceObjectDN</strong> aponta, da seguinte maneira:</p>
<ul>
<li><p>nulo | 0x00000001: representa um objeto de usuário principal do Windows NT Server de uma floresta diferente</p></li>
<li><p>Os atributos a seguir representam um tipo de grupo de uma floresta diferente para expansão do grupo de distribuição:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: representa um objeto de atendente automático ou de acesso do assinante da mesma floresta ou de uma floresta diferente</p></li>
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
<td><p>Esse atributo permite mover um usuário ou objeto de contato de um pool do Lync Server para outro. Esse atributo é adicionado à classe Contact, porque na topologia de floresta central, objetos de contato, não objetos de usuário, são SIP habilitados.</p>
<p>O valor válido é o DN do servidor de edição padrão ou do pool de front-end para o qual um usuário deve ser movido.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsoleto)</p></td>
<td><p>Este atributo de cadeia de caracteres de valor único contém um padrão ou um intervalo de números de telefone para direcionar para os gateways especificados definidos em <strong>msRTCSIP-gateways</strong>.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Esse atributo armazena pares de nome-valor para políticas de destino para usuários do Lync Server.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Tenantid</p></td>
<td><p>Esse atributo armazena o identificador exclusivo de um locatário.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-tradução (obsoleto)</p></td>
<td><p>Esse atributo é usado pelo recurso de voz do Lync Server e contém a cadeia de caracteres de tradução para aplicar o número discado, se for encontrada uma correspondência.</p></td>
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
<td><p>Esse atributo é um valor de cadeia de caracteres que contém o FQDN do MCU. Esse é um atributo de valor único. O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Esse atributo é um valor de cadeia de caracteres que contém o FQDN do servidor que está executando o servidor proxy. Esse atributo tem valor único. O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Esse atributo é reservado para uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Esse atributo é um atributo de valor único que representa o FQDN de um servidor confiável.</p></td>
<td><p>Novo no Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Esse atributo especifica o número da versão de um servidor na lista de servidores confiáveis.</p>
<p>Os valores válidos possíveis são os seguintes:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
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
<td><p>Esse atributo define as opções que são habilitadas para o serviço confiável.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Esse atributo com vários valores contém uma lista de nomes diferenciados (DN) que fazem referência a um objeto de serviço confiável, como um serviço de autenticação de retransmissão de mídia. Um serviço de autenticação de retransmissão de mídia (posicionado fisicamente no servidor de borda executando o serviço de conferência A/V) deve estar associado a um pool para dar suporte a cenários de áudio para usuários remotos.</p>
<p>O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Esse atributo é um inteiro que define o número da porta usada para se conectar a este serviço GRUU.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Esse atributo é um valor de cadeia de caracteres que define o tipo de serviço GRUU que ele representa.</p>
<p>Os tipos de serviço GRUU válidos são os seguintes:</p>
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
<td><p>Esse atributo é um valor de cadeia de caracteres que contém o FQDN do IIS que executa serviços Web do Lync Server. Esse é um atributo de valor único. O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsoleto)</p></td>
<td><p>Esse atributo define opções de comunicação unificadas diferentes que são habilitadas globalmente para todos os objetos de contato ou usuário. Esse atributo é um valor de máscara de bits do tipo inteiro. Cada opção é representada pela presença de um pouco.</p>
<p>O possível valor válido (e a posição de bit associado) são os seguintes:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (posição do bit 2)</p></li>
</ul>
<p>Quando este bit é definido, a política de UC é definida por usuário.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsoleto)</p></td>
<td><p>Esse atributo com valor único contém o DN (nome distinto) da política de UC que o administrador atribuiu para este usuário.</p></td>
<td><p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-userdomainlist (obsoleto)</p></td>
<td><p>Esse atributo fornece uma lista de todos os domínios em uma floresta que hospeda usuários habilitados para SIP. O padrão é uma lista vazia, indicando que todos os domínios na floresta são habilitados para SIP.</p>
<p>Os valores válidos são várias cadeias de caracteres que representam os nomes de domínio de domínios individuais.</p></td>
<td><p>Novo no Live Communications Server 2005.</p>
<p>Obsoleto no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Esse atributo determina se o usuário está habilitado no momento para o Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-userextension</p></td>
<td><p>Este atributo de valores múltiplos contém uma lista de pares de nomes e valores no formato de &quot;nome = valor. &quot; Esse atributo está marcado para replicação de catálogo global.</p></td>
<td><p>Novo no Live Communications Server 2005 com SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Esse atributo contém o nome diferenciado (DN) que aponta para um objeto de perfil de local.</p></td>
<td><p>Novo no Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-políticas do</p></td>
<td><p>Esse atributo armazena pares de nome-valor para políticas de usuário.</p></td>
<td><p>Novo no Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Esse é um atributo com valores múltiplos que contém uma lista de nomes diferenciados com binário (DN_WITH_BINARY) apontando para políticas de usuários globais de tipos diferentes. A parte binária indica o tipo de política para a qual a parte DN aponta.</p>
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
<td><p>Esta é a ID do grupo de roteamento SIP. Os usuários no mesmo grupo serão registrados no mesmo servidor front-end.</p></td>
<td><p>Novo no Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Esse é um atributo com vários valores. Esse atributo é reservado para uso futuro.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Esse atributo de valor único aponta para o servidor do pool ou da edição padrão ao qual os componentes Web pertencem.</p>
<p>Link encaminhar: <strong>ID do link 11028</strong></p>
<p>O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Novo no Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Esse atributo é uma lista de vários valores de nomes distintos. Esse atributo contém uma lista de todos os servidores da Web associados a este pool.</p>
<p>Link para trás: <strong>ID do link 11029</strong></p>
<p>O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
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
<td><p>Esse atributo existente do Active Directory é usado por telefonia para especificar a lista de endereços TCP/IP alternativos para um telefone.</p></td>
<td><p>Novo no sistema operacional Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Esse atributo existente do Active Directory é usado pelos componentes de voz no Lync Server, somente para objetos de contato, com a finalidade de direcionar chamadas para o atendedor automático da Unificação de mensagens e os números de acesso do Assinante. O endereço de encaminhamento de chamadas incondicionais é armazenado nesse atributo de vários valores. Esta conta é criada para o propósito específico de acesso automático e do Assinante. Os atributos da conta não devem ser modificados pelos administradores.</p></td>
<td><p>Novo no sistema operacional Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Este atributo de vários valores do Active Directory existente faz parte do esquema base do Active Directory introduzido no Windows 2000. Esse atributo contém os vários endereços X400, X500 e SMTP do email do usuário. No Live Communications Server 2003 e posterior, o URI SIP do usuário é adicionado a essa lista usando a &quot;marca SIP&quot; :.</p>
<p>Os seguintes aplicativos pesquisam o URI do SIP do usuário deste atributo:</p>
<ul>
<li><p>Cliente de mensagens e colaboração do Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Novo no sistema operacional Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Esse atributo existente do Active Directory contém o número de telefone do usuário.</p></td>
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

