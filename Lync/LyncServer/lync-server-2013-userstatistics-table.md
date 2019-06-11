---
title: 'Lync Server 2013: tabela userstatistics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a>Tabela userstatistics no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

A tabela userstatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.


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
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Número exclusivo que identifica esse usuário.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastLogInTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Última vez em que o usuário se conectou.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizedTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Última vez em que o usuário organizou uma conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>LastCallOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Última vez que o usuário experimentou uma falha na chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastConfOrganizerCallFailureTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Última vez que o usuário experimentou uma falha na chamada como um organizador de conferências.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

