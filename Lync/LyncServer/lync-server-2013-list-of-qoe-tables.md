---
title: 'Lync Server 2013: Lista de tabelas QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Lista de tabelas QoE no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

O esquema de banco de dados consiste nas tabelas a seguir.

**Tabelas de suporte**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabela</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabela AppSharingMetricsThreshold no Lync Server 2013</a></p></td>
<td><p>Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Tabela CodecDescription no Lync Server 2013</a></p></td>
<td><p>Mapeia identificadores de codec exclusivos para o codec correspondente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Tabela IPAddress no Lync Server 2013</a></p></td>
<td><p>Mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Tabela NetworkConnectionDetail no Lync Server 2013</a></p></td>
<td><p>Mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Tabela PurgeSettings (QoE) no Lync Server 2013</a></p></td>
<td><p>Armazena informações que especificam se (e quando) registros de qualidade de experiência desatualizados serão excluídos automaticamente do banco de dados de QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Tabela TraceRoute no Lync Server 2013</a></p></td>
<td><p>Armazena informações de roteamento para chamadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Tabela UserAgentDef (QoE) no Lync Server 2013</a></p></td>
<td><p>Mapeia identificadores de agente de usuário para os nomes descritivos do agente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Tabela VideoMetricsThreshold no Lync Server 2013</a></p></td>
<td><p>Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com chamadas com vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Tabela UserAgent no Lync Server 2013</a></p></td>
<td><p>Armazena cadeias de caracteres de UA (protocolo de início de sessão) do SIP e tipos de UA usados em sessões de áudio e vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Tabela User no Lync Server 2013</a></p></td>
<td><p>Armazena URIs de usuário, conferência e telefone usados em sessões de áudio e vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Tabela Endpoint no Lync Server 2013</a></p></td>
<td><p>Armazena nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Tabela Pool no Lync Server 2013</a></p></td>
<td><p>Armazena os nomes dos pools aos quais os dados de métricas pertencem.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Tabela Device no Lync Server 2013</a></p></td>
<td><p>Armazena dispositivos de captura e renderiza dispositivos que são usados em chamadas de áudio/vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Tabela DeviceDriver no Lync Server 2013</a></p></td>
<td><p>Armazena o driver para o dispositivo de captura e o dispositivo de renderização que são usados em chamadas de áudio/vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Tabela Conference no Lync Server 2013</a></p></td>
<td><p>Armazena URIs de conferência para cenários de conferência ou caixa de diálogo para outros cenários.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Tabela SessionCorrelation no Lync Server 2013</a></p></td>
<td><p>Armazena CorrelationId para chamadas PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Tabela PayloadDescription no Lync Server 2013</a></p></td>
<td><p>Armazena o codec usado em chamadas de áudio/vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabela AppliedBandwidthSource no Lync Server 2013</a></p></td>
<td><p>Armazena a fonte de largura de banda usada em chamadas de áudio/vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Tabela MacAddress no Lync Server 2013</a></p></td>
<td><p>Armazena o endereço MAC dos pontos de extremidade que participam de sessões de áudio e vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Tabela Dialog no Lync Server 2013</a></p></td>
<td><p>Armazena a ID da caixa de diálogo de sessões de áudio e vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Tabela de regiões no Lync Server 2013</a></p></td>
<td><p>Armazena a região de rede definida na configuração NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Tabela UserSite no Lync Server 2013</a></p></td>
<td><p>Armazena o site de rede definido na configuração NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Tabela Subnet no Lync Server 2013</a></p></td>
<td><p>Armazena a sub-rede definida na configuração NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Tabela MonitoredRegionLink no Lync Server 2013</a></p></td>
<td><p>Armazena o link de região definido na configuração NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Tabela MonitoredUserSiteLink</a></p></td>
<td><p>Armazena os links de sites de rede definidos na configuração NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Tabela EndpointSubnet no Lync Server 2013</a></p></td>
<td><p>Armazena a sub-rede do ponto de extremidade que participa de uma sessão de áudio e vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Tabela Server no Lync Server 2013</a></p></td>
<td><p>Armazena o FQDN ou endereço IP do servidor ao qual a mídia vai.</p></td>
</tr>
</tbody>
</table>


**Tabelas para dados de métricas**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabela</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Tabela AppSharingStream no Lync Server 2013</a></p></td>
<td><p>Armazena métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos. Métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Tabela Session no Lync Server 2013</a></p></td>
<td><p>Armazena informações gerais sobre uma sessão de áudio ou de áudio/vídeo. Uma sessão é definida como uma caixa de diálogo de áudio ou vídeo SIP entre dois pontos de extremidade.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Tabela MediaLine no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre cada linha de mídia em uma sessão. Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeo. Geralmente, uma única linha de mídia terá dois fluxos, áudio ou vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Tabela AudioStream no Lync Server 2013</a></p></td>
<td><p>Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Tabela AudioSignal no Lync Server 2013</a></p></td>
<td><p>Armazena métricas de qualidade de mídia de áudio na linha de mídia. Isso inclui as métricas de cancelamento de eco acústico (AEC) e controle automático de ganho (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Tabela VideoStream no Lync Server 2013</a></p></td>
<td><p>Armazena as métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Tabela AudioClientEvent no Lync Server 2013</a></p></td>
<td><p>Armazena métricas de qualidade da mídia de áudio coletadas do evento do cliente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Tabela VideoClientEvent no Lync Server 2013</a></p></td>
<td><p>Armazena as métricas de qualidade da mídia de vídeo coletadas do evento do cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela DiagnosticData</strong></p></td>
<td><p>Armazena dados de diagnóstico que são somente para uso interno.</p></td>
</tr>
</tbody>
</table>


**Tabelas para dados de resumo**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabela</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tabela ServerSummary</strong></p></td>
<td><p>Armazena dados de resumo para os servidores, esses dados são usados apenas para relatórios de qualidade da experiência (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabela do usersummary</strong></p></td>
<td><p>Armazena dados de resumo para os usuários, esses dados são usados somente para relatórios de QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela CallTypeSummary</strong></p></td>
<td><p>Armazenar dados de resumo para tipos de chamadas, esses dados são usados somente para relatórios de QoE.</p></td>
</tr>
</tbody>
</table>


**Tabelas para uso interno pelo Monitoring Server**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabela</strong></th>
<th><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela de front-end</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabela de tarefas</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fusos horários</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela CallSummary</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabela DeviceCallSumary</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela de locatários</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

