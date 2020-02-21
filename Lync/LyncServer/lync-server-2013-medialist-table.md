---
title: 'Lync Server 2013: tabela Medialist'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a0e59d979c3356d244bb341fcdfabae5b7addc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Tabela medialist no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-07-12_

MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.


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
<td><p><strong>Mediaid</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primário</p></td>
<td><p>Valores: 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>Mídia</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Mapeamento estático de mediaid e valores de mídia:</p>
<ul>
<li><p>1 – IM</p></li>
<li><p>2 – Transferência de arquivos</p></li>
<li><p>3 – Assistência Remota</p></li>
<li><p>4 – Compartilhamento de Aplicativos</p></li>
<li><p>5 – áudio</p></li>
<li><p>6 – vídeo</p></li>
<li><p>7 – Convite do Aplicativo</p></li>
</ul></td>
</tr>
</tbody>
</table>


Se você estiver tentando determinar o tipo de modalidade para os valores em LcsCDR. SessionDetailsView. MediaTypes, será necessário usar o trecho de junção a seguir:

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

