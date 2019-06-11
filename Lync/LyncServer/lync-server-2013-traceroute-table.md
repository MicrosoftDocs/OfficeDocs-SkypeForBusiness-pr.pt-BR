---
title: 'Lync Server 2013: tabela TraceRoute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a>Tabela TraceRoute no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-21_

A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.


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
<td><p>Primário, estrangeiro</p></td>
<td><p>Data e hora em que a chamada começou.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e ao mesmo tempo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Representa o tipo de linha de vídeo usado na chamada. Os valores permitidos são:</p>
<ul>
<li><p>0 – áudio</p></li>
<li><p>1 – vídeo</p></li>
<li><p>2 – vídeo panorâmico</p></li>
<li><p>3 – compartilhamento de aplicativos/área de trabalho</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primária</p></td>
<td><p>Ponto de extremidade que fez a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Salto de rede/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Identificador exclusivo do endereço IP. As informações de endereço IP são armazenadas na <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RESPOSTA</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Tempo de resposta. O tempo de resposta mede a quantidade de tempo que leva para um pacote de voz alcançar seu destino e enviar notificações de volta para que ele seja recebido.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

