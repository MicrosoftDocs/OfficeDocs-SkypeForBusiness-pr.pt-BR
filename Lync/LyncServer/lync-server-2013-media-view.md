---
title: 'Lync Server 2013: modo de exibição de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a>Modo de exibição de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> O modo de exibição de mídia não deve ser usado para calcular a duração da mídia de uma sessão. Este modo de exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convite não significa necessariamente a hora de início da mídia porque a mídia só inicia após a aceitação da sessão.



</div>

O modo de exibição de mídia contém todas as colunas na [exibição SessionDetails no Lync Server 2013](lync-server-2013-sessiondetails-view.md) , além das listadas abaixo.


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
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de mídia. Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Tempo em que uma solicitação de mídia foi enviada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de término da sessão.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

