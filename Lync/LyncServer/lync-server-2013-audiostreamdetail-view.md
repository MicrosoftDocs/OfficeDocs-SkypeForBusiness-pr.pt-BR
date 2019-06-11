---
title: 'Lync Server 2013: modo de exibição AudioStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10992007c76321f8ed3b436b9786cbef840173ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Exibição AudioStreamDetail no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo de dados</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sessiontime</p></td>
<td><p>datetime</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Streamid</p></td>
<td><p>int</p></td>
<td><p>ID exclusiva dentro de uma linha de mídia.</p></td>
</tr>
<tr class="even">
<td><p>StartTime </p></td>
<td><p>datetime</p></td>
<td><p>Hora de início da sessão.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Hora de término da sessão.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Categoria do diálogo: 0 é o servidor do Lync para o trecho do servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Sinalizador que indica se a chamada foi ignorada ou não.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Se presente, indica por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas. Somente um valor é definido:</p>
<p>0x0001 – ID de bypass desconhecido para o adaptador de rede padrão.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Prioridade da chamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN do pool de chamadas.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN do pool do chamador.</p></td>
</tr>
<tr class="even">
<td><p>Chamador</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>Receptor</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadeia de caracteres do agente do usuário do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente do usuário do chamador. Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria do agente do usuário do chamador. Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadeia de caracteres do agente do usuário do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente do usuário do chamador. Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria do agente do usuário do chamador. Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nome do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nome do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Sistema operacional (SO) do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Sistema operacional (SO) do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nome da CPU do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nome da CPU do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos da CPU no ponto de extremidade do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos da CPU no ponto de extremidade do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocidade do processador da CPU do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocidade do processador da CPU do ponto de extremidade do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Chave de correlação. Referenciado pela <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Informações sobre o caminho de mídia, como direta ou retransmitida. Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</p></td>
</tr>
<tr class="even">
<td><p>SMTP</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de transporte: 0 é UDP; 1 é o TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Porta usada pelo chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indica se o chamador está dentro da rede de intervalo: 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Porta usada pelo chamador.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indica se a chamada está dentro do intervalo de rede: 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nome do site do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nome do país/região do site do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nome do site do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nome do país/região do site do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta usada no serviço de borda A/V usado pelo chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Chave de endereço IP do serviço de borda A/V usado pelo chamador. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta usada no serviço de borda A/V usado pelo chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome do dispositivo de captura do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome do dispositivo de renderização do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome do driver do dispositivo de captura do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>O nome do driver de dispositivo de renderização do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome do dispositivo de captura do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome do dispositivo de renderização do Calle.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome do driver do dispositivo de captura do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Chame o nome do driver do dispositivo de processamento do recurso.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica se o chamador está conectado por meio de uma rede privada virtual: 1 é uma rede virtual privada (VPN), 0 não é VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal (18, 0)</p></td>
<td><p>Velocidade do link de rede para o ponto de extremidade do chamador em bps.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica se o chamador está conectado por meio de uma rede privada virtual: 1 é uma rede virtual privada (VPN), 0 não é VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal (18, 0)</p></td>
<td><p>Velocidade do link de rede para o ponto de extremidade do chamador em bps.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>A largura de banda real aplicada ao fluxo de envio do lado fornecido tem várias configurações de política (ativar, API, SDP, servidor de política e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Maior tremulação de rede durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimal (5, 4)</p></td>
<td><p>Taxa média de perda de pacotes durante a chamada.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal (5, 4)</p></td>
<td><p>Perda máxima de pacote observado durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Densidade média de perda de pacote durante intermitências de perdas durante a chamada.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Duração média da perda de pacote durante intermitências de perdas durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Densidade média de perda de pacote durante intervalos entre intermitências de perda de pacote.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Duração média de lacunas entre intermitências de perda de pacote.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Contagem de pacotes para o fluxo de áudio.</p></td>
</tr>
<tr class="even">
<td><p>Largura de banda</p></td>
<td><p>int</p></td>
<td><p>Estimativas de largura de banda para o fluxo de áudio.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Degradação do MOS de rede para toda a chamada. O intervalo é de 0,0 a 5,0. Essa métrica mostra o valor que o MOS de rede foi reduzido devido à instabilidade e à perda de pacote. Para ter uma qualidade aceitável, ele deve ser menor do que 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Degradação do MOS de rede máxima durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Degradação de MOS de rede causada pela tremulação.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Degradação de MOS de rede causada por perda de pacote.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>O codec de áudio usado para a chamada, referenciado pela <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Taxa de amostragem do fluxo de áudio.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>O nível de sinal de áudio pós-analógico de controle de ganho para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de sinal de áudio para o áudio recebido pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio recebido pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Aprimoramento da perda de retorno de eco para o chamador. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Média de falhas por cinco minutos para a renderização de alto-falante do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Média de falhas por cinco minutos para a captura de microfone do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Taxa de descompasso do relógio do dispositivo de microfone do chamador, relativa ao relógio da CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Taxa de descompasso do relógio do dispositivo de alto-falante do chamador em relação ao relógio da CPU.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Média do alto-falante do chamador processar carimbo de data/hora do fluxo, em milissegundos, nos últimos 20 segundos da chamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida. Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causa de um evento de eco para o chamador. Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal (5; 2)</p></td>
<td><p>Porcentagem de tempo em que o eco é detectado no fluxo de captura de microfone do chamador. Se o fone de ouvido estiver sendo usado, o valor deve ser baixo.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal (5; 2)</p></td>
<td><p>Porcentagem de tempo em que o eco é detectado no fluxo de envio do chamador. Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador; Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser de-30 a-18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador. Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Controle de ganho automático (AGC) no lado do servidor de mediação aplicado ao áudio do chamador.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>A base média (RMS) do sinal de entrada para o chamador para até os primeiros 30 segundos da chamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Representa o nível de sinal de áudio de controle de ganho de cruz analógico para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de sinal de áudio para o áudio que o chama recebido. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio que o chamador recebeu. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Aprimoramento da perda de retorno de eco para o chamador. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Média de falhas por cinco minutos para a renderização do alto-falante do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Média de falhas por cinco minutos para a captura de microfone do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Taxa de descompasso do relógio do dispositivo de microfone do chamador, em relação ao relógio da CPU.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Taxa de descompasso do relógio do dispositivo de alto-falante do chamador, em relação ao relógio da CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Média do erro de carimbo de data/hora do fluxo de processamento do palestrante em milissegundos, nos últimos 20 segundos da chamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida. Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causas de um evento de eco para o chamador. Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal (5; 2)</p></td>
<td><p>Porcentagem de tempo em que o eco é detectado no fluxo de captura do microfone do chamador. Se o fone de ouvido estiver sendo usado, o valor deve ser baixo.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal (5; 2)</p></td>
<td><p>Porcentagem de tempo em que o eco é detectado no fluxo enviado do chamador. Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador; Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser [-30 a-18] dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador. Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Controle de ganho automático (AGC) no lado do servidor de mediação aplicado ao áudio do chamador.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>A base média (RMS) do sinal de entrada para o receptor para até os primeiros 30 segundos da chamada.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal (5; 2)</p></td>
<td><p>Índice médio de amostras ocultas geradas pelo reparo de áudio para amostras típicas.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal (5; 2)</p></td>
<td><p>Índice médio de amostras ampliadas geradas pelo reparo de áudio para amostras típicas.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal (5; 2)</p></td>
<td><p>Índice médio de amostras compactadas geradas pelo reparo de áudio para amostras típicas.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Tempo de ida e volta das estatísticas do RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Tempo máximo de ida e volta do fluxo de áudio.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Banda larga médio de um MOS de rede para a chamada. Essa métrica depende da perda de pacotes, da tremulação e do codec usados. O intervalo é de 1,0 a 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Banda larga de rede mínima para a chamada.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Pontuação estimada banda larga de escuta da MOS para áudio enviado, incluindo o nível de fala, o nível de ruído e as características do dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>SendListenMOS mínima para a chamada.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>Média prevista banda larga ouvindo a Pontuação do MOS para áudio recebido da rede, incluindo o nível de fala, o nível de ruído, o codec, as condições da rede e as características do dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal (3; 2)</p></td>
<td><p>RecvListenMOS mínima para a chamada.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>Indica se o FEC de áudio foi usado para a chamada.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Indica a direção das informações de identificação p-declaradas; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

