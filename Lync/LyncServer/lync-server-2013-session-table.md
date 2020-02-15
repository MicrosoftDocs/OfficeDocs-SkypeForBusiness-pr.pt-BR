---
title: 'Lync Server 2013: tabela de sessão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c252ef5cd96511875fa299f44ca2a707f766f59a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Tabela de sessão no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-09-09_

Cada registro representa uma sessão que envolve áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo de áudio ou protocolo SIP entre dois pontos de extremidade.


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
<td><p>Primário</p></td>
<td><p>Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de diálogo no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário</p></td>
<td><p>Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de diálogo no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Chave de conferência. Referenciado da <a href="lync-server-2013-conference-table.md">tabela de conferência no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Chave de correlação. Referenciado da <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bits</p></td>
<td><p> </p></td>
<td><p>Categoria da caixa de diálogo; 0 é o servidor do Lync Server para o trecho do servidor de mediação; 1 é o servidor de mediação para o segmento de gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Sinalizador que indica se a chamada foi ignorada ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem. Para o Lync Server, apenas um valor é definido.</p>
<p>0x0001 - ID de desvio desconhecida ao adaptador de rede padrão.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora do início da chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora da finalização da chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O pool do chamador. Referenciado da <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O pool do receptor de chamada. Referenciado da <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O URI do SIP na PAI (identidade do SIP p-Asserted) do ponto de extremidade de recebimento. Referenciado da <a href="lync-server-2013-user-table.md">tabela user no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>URI do chamador. Referenciado da <a href="lync-server-2013-user-table.md">tabela user no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Ponto de extremidade do chamador. Referenciado da <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bits</p></td>
<td><p>Estrangeira</p></td>
<td><p>Agente do usuário do chamador. Referenciado da <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>A prioridade desta chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Esta coluna foi preterida e não é usada no Microsoft Lync Server 2013. Em vez disso, essas informações são relatadas em uma base de linha por mídia. Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>P-Asserted-Identity do usuário que fez a chamada. O P-Asserted-Identity (PAI) é usado para transmitir a identidade real do usuário que fez a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Ponto de extremidade que recebeu a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O agente do usuário empregado pelo usuário que recebeu a chamada. Os agentes de usuário representam o dispositivo de ponto de extremidade do cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>URI do SIP do usuário que recebeu a chamada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

