---
title: 'Lync Server 2013: Tabela Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Tabela Session no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-09-09_

Cada registro representa uma sessão que envolve áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo de protocolo de iniciação de sessão de áudio ou de vídeo (SIP) entre dois pontos de extremidade.


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
<td><p>Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de caixa de diálogo no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de caixa de diálogo no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Chave de conferência. Referenciado na <a href="lync-server-2013-conference-table.md">tabela de conferências no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Chave de correlação. Referenciado pela <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Categoria da caixa de diálogo; 0 é o servidor do Lync para o segmento do servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Sinalizador que indica se a chamada foi ignorada ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Esse campo, se presente, indicará por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas. Para o Lync Server, somente um valor é definido.</p>
<p>0x0001 – ID de bypass desconhecido para o adaptador de rede padrão.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime </strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de início da chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de término da chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O pool do chamador. Referenciado na <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O pool do receptor da chamada. Referenciado na <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O URI de SIP na identidade SIP p-declarated (PAI) do ponto de extremidade de recebimento. Referenciado da <a href="lync-server-2013-user-table.md">tabela de usuário no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>URI do chamador. Referenciado da <a href="lync-server-2013-user-table.md">tabela de usuário no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Ponto de extremidade do chamador. Referenciado na <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>Exterior</p></td>
<td><p>Agente de usuário do chamador. Referenciado na <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>A prioridade desta chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Esta coluna foi preterida e não é usada no Microsoft Lync Server 2013. Em vez disso, essas informações são relatadas em bases de linhas por mídia. Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>P-declarado-identidade do usuário que fez a chamada. A identidade de P-declarada (PAI) é usada para transmitir a verdadeira identidade do usuário que fez a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Ponto de extremidade que recebeu a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Agente de usuário empregado pelo usuário que recebeu a chamada. Os agentes de usuário representam o dispositivo de ponto de extremidade do cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O URI SIP do usuário que recebeu a chamada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

