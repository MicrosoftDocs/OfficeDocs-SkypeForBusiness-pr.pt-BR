---
title: 'Lync Server 2013: tabela SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2418851ed66500937dab92f2820c36a8d1afac3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519628"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Tabela SIPResponseMetaData no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um destes códigos. Estes códigos são gerados em resposta aos eventos que afetam dispositivos SIP e sessões de comunicação SIP. Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor declina esta solicitação.

Esta tabela foi introduzida no Microsoft Lync Server 2013.


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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Primário</p></td>
<td><p>Valor numérico que representa o código de resposta SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Classe</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Classificação geral do código de resposta. As classificações incluem:</p>
<ul>
<li><p>1 – Respostas informacionais</p></li>
<li><p>2 – Respostas de sucesso</p></li>
<li><p>3 – Respostas de redirecionamento</p></li>
<li><p>4 – Respostas de falha do cliente</p></li>
<li><p>5--respostas de falha do servidor</p></li>
<li><p>6 – Resposta de falha global</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Descrição</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Descrição do código de resposta SIP. Por exemplo, o código de resposta 181 possui a seguinte descrição:</p>
<p>A chamada está sendo encaminhada</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

