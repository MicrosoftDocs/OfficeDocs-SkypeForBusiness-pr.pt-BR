---
title: 'Lync Server 2013: Tabela ErrorDef'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55a6ab9a8bf50639267824c8330701ee74cb3f5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a>Tabela ErrorDef no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-05-25_

A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.


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
<td><p><strong>ErrorID</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Número de identificação exclusivo que identifica esse tipo de erro.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Código de resposta SIP padrão associado a esse erro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>IDENTIFICAÇÃO do diagnóstico da Microsoft.</p></td>
</tr>
<tr class="even">
<td><p><strong>Callid</strong></p></td>
<td><p>Núm</p></td>
<td><p>Exterior</p></td>
<td><p>Tipo de chamada. Consulte a <a href="lync-server-2013-calltype-table.md">tabela CallType no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary (33)</p></td>
<td><p> </p></td>
<td><p>Tipo de solicitação que falhou.</p>
<p>Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary (257)</p></td>
<td><p> </p></td>
<td><p>Tipo de conteúdo da solicitação que falhou.</p>
<p>Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

