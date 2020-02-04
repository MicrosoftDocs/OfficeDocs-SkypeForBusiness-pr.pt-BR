---
title: 'Lync Server 2013: Tabela CallPriorities'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31ddf598fcf33b4f4841f9e3a9e857fd57ea608c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a>Tabela CallPriorities no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamadas, como ' emergência ', ' urgente ' ou ' normal '.


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
<td><p><strong>Priorityid</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primária</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Prioridade</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0-desconhecido</p></li>
<li><p>1 – não urgente</p></li>
<li><p>2-normal</p></li>
<li><p>3-urgente</p></li>
<li><p>4-emergência</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

