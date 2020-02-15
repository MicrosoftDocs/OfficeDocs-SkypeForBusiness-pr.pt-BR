---
title: 'Lync Server 2013: tabela ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 143e2b44c5b5ddd9cbf630ac17267e0747029aed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>Tabela ConferenceUris no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-05-25_

A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo de dados</th>
<th>Chave/índice</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primário</p></td>
<td><p>Carimbo de hora, Interno usado.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Primário</p></td>
<td><p>Número exclusivo que identifica o URI desta conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conferenceui</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>URI da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Soma de verificação</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Soma de verificação do ConferenceUri. Usado para aumentar a velocidade de pesquisas no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Tipo de URI, por exemplo, conf:chat para conferência IM ou conf:audio-video para conferência de áudio/vídeo. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes na tabela do Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

