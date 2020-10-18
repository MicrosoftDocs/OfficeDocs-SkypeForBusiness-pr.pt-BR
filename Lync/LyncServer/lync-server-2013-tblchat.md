---
title: 'Lync Server 2013: tblChat'
description: 'Lync Server 2013: tblChat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e68d4f0d1ca7ae227c78c95d02e02ffc81656feb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573647"
---
# <a name="tblchat-in-lync-server-2013"></a>tblChat no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-12_

A tabela tblChat contém todas as mensagens de chat.

### <a name="columns"></a>Colunas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelId</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID do nó.</p></td>
</tr>
<tr class="even">
<td><p>chatid</p></td>
<td><p>bigint, não nulo</p></td>
<td><p>Número sequencial exclusivo (por ID do nó) que define a ordem da sala de chat, gerado pela tabela tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, não nulo</p></td>
<td><p>Carimbo de hora para a mensagem de chat.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID principal do pôster.</p></td>
</tr>
<tr class="odd">
<td><p>isalert</p></td>
<td><p>bit, não nulo</p></td>
<td><p>True se a mensagem for uma mensagem de alerta.False se não for.</p></td>
</tr>
<tr class="even">
<td><p>conteúdo</p></td>
<td><p>nvarchar (max), não nulo</p></td>
<td><p>Conteúdo de chat (a versão de texto). O conteúdo está normalmente em texto sem formatação com as seguintes exceções:</p>
<ul>
<li><p>Os arquivos são representados como links ma-filelink:.</p></li>
<li><p>Links são representados como um elemento HTML (embora o tipo de conteúdo não possa ser considerado HTML).</p></li>
<li><p>Histórias são codificadas como um formato parecido com “[STORY]....”.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>formato</p></td>
<td><p>varchar (max)</p></td>
<td><p>Conteúdo do chat (a versão RTF). Pode ser Nulo se o cliente não o fornecer.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Chave

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;channelId, em bate-papo&gt;</p></td>
<td><p>Chave primária.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

