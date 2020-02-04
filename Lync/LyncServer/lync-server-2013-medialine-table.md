---
title: 'Lync Server 2013: Tabela MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Tabela MediaLine no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-21_

Cada registro representa uma linha de mídia. (Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Coluna</strong></th>
<th><strong>Tipo de dados</strong></th>
<th><strong>Chave/índice</strong></th>
<th><strong>Detalhes</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-session-table.md">tabela de sessão no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primária</p></td>
<td><p>0 é o áudio principal, 1 é o vídeo principal e 2 é o vídeo panorâmico, 3 é o compartilhamento de aplicativos/desktop. Esse rótulo deve ser exclusivo em uma única sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Esta coluna está presente, mas não é usada no Microsoft Lync Server 2013. Informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits. Para obter detalhes, consulte a <em>especificação de protocolo de servidor do monitoramento de qualidade de experiência</em>, disponível para download.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Mesmo que CallerIceWarningFlags, mas no lado do chamador. Para obter detalhes, consulte a <em>especificação de protocolo de servidor do monitoramento de qualidade de experiência</em>, disponível para download.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Segurança</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>O perfil de segurança em uso. 0 é nenhum, 1 é SRTP; 2 é v1.</p></td>
</tr>
<tr class="even">
<td><p><strong>SMTP</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 é UDP; 1 é TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço IP do chamador. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta usada pelo chamador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> Exterior</p></td>
<td><p>A sub-rede do chamador. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço MAC do chamador, referenciado na <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço IP do serviço de borda a/V do Lync Server usado pelo chamador. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta usada no serviço de borda A/V pelo chamador.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Dispositivo de captura usado pelo chamador. Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Processar o dispositivo usado pelo chamador. Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Driver para o dispositivo de captura do chamador, referenciado na <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Driver para o dispositivo de renderização do chamador, referenciado na <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Exterior</p></td>
<td><p>Indica como o chamador está conectado à rede. Os valores são obtidos na <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>. Os valores típicos são 0 para uma conexão com fio ' 1 para conexão WiFi; e 3 para uma conexão Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>BSSID do chamador se for usada uma conexão sem fio. Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>O link do chamador. 1 é uma rede virtual privada (VPN), 0 não é VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal (18, 0)</p></td>
<td></td>
<td><p>A velocidade do link de rede, em bps, para o ponto de extremidade do chamador.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço IP do receptor da chamada. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Porta usada pelo receptor da chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Sub-rede do chamado. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que o receptor da chamada está dentro da rede corporativa, 0 significa que o receptor da chamada está fora da rede.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço MAC do chamador. Referenciada na <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço IP do serviço de borda A/V usado pelo receptor de chamadas. Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Porta usada no serviço de borda a/V pelo receptor da chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>exterior</p></td>
<td><p>Dispositivo de captura usado pelo receptor de chamadas. Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Processar o dispositivo usado pelo receptor da chamada. Referenciado da <a href="lync-server-2013-device-table.md">tabela de dispositivos no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Driver para o dispositivo de captura do receptor da chamada. Referenciado pela <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>Exterior</p></td>
<td><p>Driver para o dispositivo de renderização do receptor da chamada. Referenciado pela <a href="lync-server-2013-devicedriver-table.md">tabela DeviceDriver no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Exterior</p></td>
<td><p>Indica como o chamador está conectado à rede. Os valores são obtidos na <a href="lync-server-2013-networkconnectiondetail-table.md">tabela NetworkConnectionDetail no Lync Server 2013</a>. Os valores típicos são 0 para uma conexão com fio ' 1 para conexão WiFi; e 3 para uma conexão Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>BSSID do chamador se for usada uma conexão sem fio. Referenciado da <a href="lync-server-2013-macaddress-table.md">tabela MACAddress no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>O link do receptor da chamada; 1 é uma rede virtual privada (VPN), 0 não é VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal (18, 0)</p></td>
<td><p> </p></td>
<td><p>A velocidade do link de rede, em bps, para o ponto de extremidade do receptor da chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Esta é a largura de banda real aplicada ao fluxo de envios do lado fornecido com várias configurações de política (ativar, API, SDP, servidor de política e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Essa é a origem do limite de largura de banda que está sendo imposto. Ele descreve onde o limite de largura de banda é proveniente de ("servidor de políticas", "Ativar servidor", "Janelarestritaidade" e assim por diante). Referenciado pela <a href="lync-server-2013-appliedbandwidthsource-table.md">tabela AppliedBandwidthSource no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamador</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica se as métricas do autor foram recebidas; 1 é sim, um valor nulo é não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Receptor</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, um valor nulo é não.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica se o relatório é para uma parte da sessão ou para a sessão completa.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica se uma chamada foi classificada como uma chamada ruim (valor 1) ou uma boa chamada (0).</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço IP reflexivo do usuário que fez a chamada. Em organizações que usam NAT (Network Address Translation), o endereço IP reflexivo é o endereço IP do servidor proxy.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Número da versão do driver WiFi empregado pelo usuário que fez a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Endereço IP reflexivo do usuário que recebeu a chamada. Em organizações que usam NAT (Network Address Translation), o endereço IP reflexivo é o endereço IP do servidor proxy.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Descrição do dispositivo para o driver WiFi empregado pelo usuário que recebeu a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Número da versão do driver WiFi empregado pelo usuário que recebeu a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

