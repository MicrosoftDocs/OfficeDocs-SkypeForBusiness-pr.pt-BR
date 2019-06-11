---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a>tblScopePrincipal no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblScopePrincipal contém escopos atribuídos a nós.

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
<td><p>scopeNodeID</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID do nó ao qual o escopo se aplica.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança.</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se o tipo de escopo for negar; Falso se permitir.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança que atualizou pela última vez esta entrada.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>As

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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblNode. NodeId.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

