---
title: 'Lync Server 2013: tblPrincipalMembers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b35af88b4b1c0e32ceb6af97b379ded66b437f7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a>tblPrincipalMembers no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblPrincipalMembers contém associações de entidades de segurança.

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
<td><p>multiimprimir</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança.</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar (384), NOT NULL</p></td>
<td><p>Nome diferenciado de um membro. Um membro não precisa ser um principal (na tabela tblPrincipal).</p></td>
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
<td><p>&lt;memberADPath&gt;</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>multiimprimir</p></td>
<td><p>Chave estrangeira com Lookup em tblPrincipal. importaid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

