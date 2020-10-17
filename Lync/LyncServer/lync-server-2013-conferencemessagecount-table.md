---
title: 'Lync Server 2013: tabela ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae806fc50fb0d4c4936fb6fbf6f879f4d4fc2ce4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529328"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a>Tabela ConferenceMessageCount no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Cada registro desta tabela representa um usuário em uma conferência de mensagens instantâneas e inclui o número de mensagens enviadas por esse usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.


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
<td><p><strong>Identificação_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primário, externo</p></td>
<td><p>Hora da instância da conferência. Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, externo</p></td>
<td><p>Número de ID para identificar a instância da conferência. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>O número de mensagens enviadas por esse usuário durante esta conferência.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

