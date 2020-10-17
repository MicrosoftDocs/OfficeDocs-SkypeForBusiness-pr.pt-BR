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
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505718"
---
# <a name="medialist-table-in-lync-server-2013"></a>Tabela medialist no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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

