---
title: 'Lync Server 2013: Tabela FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Tabela FileTransfers no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Cada registro representa uma sessão de transferência de arquivo.


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
<td><p><strong>Id_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Tempo de solicitação de sessão. Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nome do arquivo</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Nome do arquivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fileidentity</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Identificador exclusivo para distinguir entre as transferências de arquivo que envolvem o mesmo nome de arquivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Primária</p></td>
<td><p>Usado para identificar todas as mensagens de acompanhamento como associadas a esta.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aceite</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Pode ser TRUE ou NULL. Se verdadeiro, rejeitar e cancelar será nulo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rejeitar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Pode ser TRUE ou NULL. Se verdadeiro, aceitar e cancelar será nulo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancelar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Pode ser TRUE ou NULL. Se verdadeiro, aceitar e rejeitar será nulo.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

