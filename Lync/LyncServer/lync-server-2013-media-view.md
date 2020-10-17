---
title: 'Lync Server 2013: modo de exibição de mídia'
description: 'Lync Server 2013: modo de exibição de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558007"
---
# <a name="media-view-in-lync-server-2013"></a>Exibição de mídia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> A exibição de mídia não deve ser usada para calcular a duração de mídia para uma sessão. Essa exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação INVITE, e o StartTime indica o horário em que o INVITE foi enviado. O horário de convite não significa, necessariamente, o horário de início da mídia, pois a mídia só começa depois que a sessão tenha sido aceita.



</div>

O modo de exibição de mídia contém todas as colunas no [modo de exibição SessionDetails no Lync Server 2013](lync-server-2013-sessiondetails-view.md) , além das listadas abaixo.


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
<td><p><strong>Mídia</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de mídia. Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Horário em que a solicitação de mídia foi enviada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Horário de término da sessão.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

