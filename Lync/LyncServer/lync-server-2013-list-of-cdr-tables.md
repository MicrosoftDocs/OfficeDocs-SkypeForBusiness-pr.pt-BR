---
title: 'Lync Server 2013: Lista de tabelas CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lista de tabelas do CDR no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

O esquema de banco de dados de registro de detalhes de chamadas (CDR) consiste nas tabelas a seguir.

<div>

## <a name="static-tables"></a>Tabelas estáticas


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Tabela CallPriorities no Lync Server 2013</a></p></td>
<td><p>Armazena a lista de prioridades de chamadas possíveis, como emergência, urgente, normal, não urgente e muito mais.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabela ConferenceJoinTimeThresholds no Lync Server 2013</a></p></td>
<td><p>Armazena os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Tabela DeRegisterType no Lync Server 2013</a></p></td>
<td><p>Armazena a lista de possíveis motivos de descadastramento do usuário, &quot;como o cliente&quot; &quot;iniciado, o&quot; &quot;registro expirou,&quot; a falha do cliente e muito mais.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Tabela MediaList no Lync Server 2013</a></p></td>
<td><p>Armazena a lista de tipos de mídia que podem gerar entradas no banco de dados (por exemplo, mensagens instantâneas, áudio, vídeo e transferência de arquivos).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Tabela PurgeSettings no Lync Server 2013</a></p></td>
<td><p>Armazena informações que especificam se (e quando) registros de detalhes de chamadas desatualizadas serão automaticamente excluídos do banco de dados CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Tabela Roles no Lync Server 2013</a></p></td>
<td><p>Armazena a lista de possíveis funções de conferência (por exemplo, participante e apresentador).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Tabela SIPResponseMetaData no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Tabelas de suporte


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Tabela ClientVersions no Lync Server 2013</a></p></td>
<td><p>Armazena os clientes (o tipo de cliente e o número da versão) de cada cliente envolvido em uma chamada com informações capturadas nesse banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Tabela ConferenceUris no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de ConferenceURIs que são usadas em chamadas relacionadas à conferência.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Tabela ContentTypes no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de tipos de conteúdo de protocolo SIP que são usados em chamadas ponto a ponto e em chamadas em conferência.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Tabela Devices no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de dispositivos, incluindo o fabricante, a versão de hardware e o endereço MAC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Tabela Dialogs no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre a ID da caixa de diálogo para cada sessão do banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Tabela EdgeServers no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de servidores de borda que são usados para chamadas externas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Tabela Gateways no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de gateways que são usados para chamadas de protocolo de voz por Internet (VoIP).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Tabela HardwareVersions no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de versões de hardware de dispositivos (telefone de mesa).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Tabela Manufacturers no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de fabricantes de dispositivos (telefone de mesa).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Tabela Mcus no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre os vários servidores de conferência A/V e seus URIs.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Tabela MediationServers no Lync Server 2013</a></p></td>
<td><p>Armazena uma lista de servidores de mediação que são usados para chamadas VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Tabela Phones no Lync Server 2013</a></p></td>
<td><p>Armazena todos os números de telefone usados em chamadas VoIP que foram arquivadas ou cujos detalhes da chamada foram registrados.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Tabela Pools no Lync Server 2013</a></p></td>
<td><p>Armazena os nomes do pool no qual as mensagens INSTANTÂNEAs são capturadas.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Tabela de servidores no Lync Server 2013</a></p></td>
<td><p>Armazena o nome dos servidores envolvidos nas chamadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Tabela Tenants no Lync Server 2013</a></p></td>
<td><p>Armazena os locatários compatíveis com a implantação atual. Há alguns locatários de compilação para usuários corporativos, usuários federados, usuários de conectividade de mensagens de chat públicas e usuários anônimos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Tabela UserAgentDef no Lync Server 2013</a></p></td>
<td><p>Mapeia identificadores de agente de usuário para os nomes descritivos do agente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Tabela Users no Lync Server 2013</a></p></td>
<td><p>Armazena o usuário URIs de usuários que participaram de sessões registradas ou arquivadas neste banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Tabela userstatistics no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre o uso de um usuário individual do sistema.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Tabelas específicas para registros de CDR em conferência


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Tabela Conferences no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre todas as conferências que foram arquivadas ou cujos detalhes foram registrados, incluindo ConferenceURI e hora de início e de término.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Tabela ConferenceSessionDetails no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre cada sessão de conferência baseada em SIP, incluindo hora de início e de término, ID de usuário, código de resposta e identificação de diagnóstico para cada sessão.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabela FocusJoinsAndLeaves no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre junções e folhas de conferência, incluindo a função do usuário e a versão do cliente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabela McuJoinsAndLeaves no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre os servidores de conferência A/V envolvidos em uma conferência e o usuário ingressa e sai do tempo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Tabelas de mensagens em conferências de mensagens INSTANTÂNEAs


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Tabela ConferenceMessageCount no Lync Server 2013</a></p></td>
<td><p>Para cada conferência de mensagem instantânea, armazena o número de mensagens enviadas por cada usuário.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Tabela IMReportSummary no Lync Server 2013</a></p></td>
<td><p>Fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Tabelas para sessões ponto a ponto


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Tabela SessionDetails no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre cada sessão ponto a ponto, incluindo a hora de início e de término, a ID de usuário, o código de resposta e a contagem de mensagens para cada usuário.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Tabela FileTransfers no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre sessões de transferência de arquivos, incluindo o resultado e o resultado (aceito, rejeitado ou cancelado).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Tabela Media no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre os diferentes tipos de mídia envolvidos em sessões ponto a ponto.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Tabela para detalhes da chamada VoIP


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Tabela VoipDetails no Lync Server 2013</a></p></td>
<td><p>Para cada chamada VoIP/PSTN de dois participantes, armazena informações sobre a chamada, como a ID do telefone de VoIP, o gateway usado e a parte desconectada. Refere-se à <a href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</a> para tempo de início/término e código de resposta de chamada.</p>
<div>

> [!NOTE]  
> Se um participante de uma chamada for um usuário de VoIP ou se um servidor de mediação estiver envolvido na chamada, um registro será criado nessa tabela. As informações sobre chamadas VoIP/VoIP que não envolvem um telefone PSTN (rede telefônica pública comutada) são capturadas na <A href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Tabela para auditoria de chamada E9-1-1


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Tabela Locations no Lync Server 2013</a></p></td>
<td><p>Para cada chamada de emergência, como uma chamada Enhanced 9-1-1 (E9-1-1), armazena informações de localização sobre a chamada. Refere-se à <a href="lync-server-2013-sessiondetails-table.md">tabela SessionDetails no Lync Server 2013</a> para tempo de início/término e código de resposta de chamada.</p>
<div>

> [!NOTE]  
> Esta tabela contém apenas o blob de localização para a chamada E9-1-1. Refere-se à tabela SessionDetails para obter outras informações detalhadas sobre a chamada.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tabelas para solução de problemas


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Tabela de aplicativos no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre vários processos no Lync Server 2013 que estão envolvidos em roteamento e conexões.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Tabela CallType no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre tipos de chamada, como "áudio", "mensagens instantâneas", "áudio e vídeo" e "compartilhamento de aplicativos".</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Tabela ErrorCategory no Lync Server 2013</a></p></td>
<td><p>Armazena o nome amigável para cada classificação de diagnóstico do Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Tabela ErrorDef no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre tipos de erros e suas definições.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Tabela ErrorReport no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre erros ocorridos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Tabela ProgressReport no Lync Server 2013</a></p></td>
<td><p>Armazena informações sobre os relatórios de progresso de várias etapas envolvidas nos processos do Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


As tabelas na lista a seguir são usadas internamente pelo Lync Server. Seus detalhes não estão descritos neste documento.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Tabelas para uso interno pelo Lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabela</th>
<th>Descrição</th>
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
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabela de front-end</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela MSMQProcessing</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela de sindicadores</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabela SyndicatorsTenantMap</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabela de tarefas</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fusos horários</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Somente para uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

