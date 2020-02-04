---
title: 'Lync Server 2013: modo de exibição VoIPDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db65da0af7c34d1121e97436af47750186706b68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a>Exibição VoIPDetails no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> A exibição VoIPDetails contém todas as colunas na <A href="lync-server-2013-sessiondetails-view.md">exibição SessionDetails do Lync Server 2013</A> , além das colunas listadas abaixo.



</div>


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
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do telefone do usuário que iniciou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Por telefone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do telefone do usuário que ingressou na sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URL do usuário que desconectou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI do usuário que desconectou a sessão. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locatário do usuário que desconectou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do telefone do usuário que desconectou a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediação usado pelo usuário que iniciou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediação usado pelo usuário que ingressou na sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>O gateway usado pelo usuário que iniciou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Togateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>O gateway usado pelo usuário que ingressou na sessão.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

