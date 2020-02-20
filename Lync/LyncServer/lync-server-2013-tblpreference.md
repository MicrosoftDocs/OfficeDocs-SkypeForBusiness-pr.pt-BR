---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9d91a11f6813bfc7ef86eaf5efded41c7af0c63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a>tblPreference no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-24_

tblPreference contém as preferências de cliente do usuário. Isso geralmente é usado por clientes anteriores ao Lync 2013.

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
<td><p>prefLabel</p></td>
<td><p>nvarchar (255), não nulo</p></td>
<td><p>Rótulo com um formato como: &lt;User SIP URI&gt;| username. &lt;definição&gt;de preferência.</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int, not null</p></td>
<td><p>Um número sequencial (por rótulo) para fins de controle de versão.</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (máx.)</p></td>
<td><p>Conteúdo codificado.</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int, not null</p></td>
<td><p>ID da entidade de segurança que atualizou a preferência.</p></td>
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
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>Chave primária.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

