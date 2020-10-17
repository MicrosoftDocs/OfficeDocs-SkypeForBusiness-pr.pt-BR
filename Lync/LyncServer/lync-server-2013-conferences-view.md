---
title: 'Lync Server 2013: modo de exibição de conferências'
description: 'Lync Server 2013: modo de exibição de conferências.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561577"
---
# <a name="conferences-view-in-lync-server-2013"></a>Exibição de conferências no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

A Exibição de Conferências armazena informações sobre as conferências. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo de dados</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identificação_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conferenceui</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo da URI de conferência. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>identificador</p></td>
<td><p>Usado para conferências recorrentes. Cada instância de uma conferência recorrente possui o mesmo ConferenceUri, mas um ConfInstance diferente.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora inicial da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora final da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do usuário que organizou a conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OrganizerType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI do usuário que organizou a conferência. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Inquilino do usuário que organizou a conferência. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome de domínio totalmente qualificado do pool que hospeda a conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Máscara de bits que contém os Atributos de Conferência. Os possíveis valores são:</p>
<p>0X01 – Transação Sintética</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

