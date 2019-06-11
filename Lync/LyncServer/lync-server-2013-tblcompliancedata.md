---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044a57645a8c49ea74ec4e003f9e12720d0b2268
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>tblComplianceData no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblComplianceData contém os eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.

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
<td><p>cmplEventID</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>ID do evento.</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, não nulo</p></td>
<td><p>Tempo de inserção (pode estar muito no futuro para cmplType = 9 porque a entrada é apenas um espaço reservado nesse caso).</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, não nulo</p></td>
<td><p>Tipo de evento de conformidade:</p>
<ul>
<li><p>1: chat</p></li>
<li><p>2: backchat</p></li>
<li><p>3: download de arquivo</p></li>
<li><p>4: carregamento de arquivo</p></li>
<li><p>9: transferência de arquivo provisório</p></li>
<li><p>10: exclusão de chat (com replace)</p></li>
<li><p>11: limpeza de chat</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Carimbo de data/hora do evento.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255), NOT NULL</p></td>
<td><p>URI (Uniform Resource Identifier) do canal.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>ID de chat (correspondente à tabela tblChat. chatid).</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança do pôster (correspondente à tabela tblPrincipal. retoid).</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255), NOT NULL</p></td>
<td><p>URI de usuário.</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Mensagem (a codificação depende do cmplType).</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>Chave primária.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

