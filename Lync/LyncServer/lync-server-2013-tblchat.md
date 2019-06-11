---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 620dcb49580f8d19a8f262c22b1005e3cefeac4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblChat contém todas as mensagens de chat.

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
<td><p>chats</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Número seqüencial exclusivo (por ID do nó) que define o pedido de sala de chat, gerado pela tabela tblLastChatId.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Carimbo de data/hora para a mensagem de chat.</p></td>
</tr>
<tr class="even">
<td><p>ID</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança do pôster.</p></td>
</tr>
<tr class="odd">
<td><p>isalert</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se a mensagem for uma mensagem de alerta. Falso se não for.</p></td>
</tr>
<tr class="even">
<td><p>disputa</p></td>
<td><p>nvarchar (max), NOT NULL</p></td>
<td><p>Conteúdo de chat (a versão de texto sem formatação). O conteúdo geralmente está em texto sem formatação com as seguintes exceções:</p>
<ul>
<li><p>Os arquivos são representados como links ma-filelink: links.</p></li>
<li><p>Os links são representados como um elemento HTML (embora o tipo de conteúdo não possa ser considerado HTML).</p></li>
<li><p>As matérias são codificadas como um formato "[história]..."-como.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>me</p></td>
<td><p>varchar (max)</p></td>
<td><p>Conteúdo de chat (a versão RTF). Pode ser NULL se o cliente não fornecê-lo.</p></td>
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
<td><p>&lt;channelId, em chat&gt;</p></td>
<td><p>Chave primária.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

