---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>tblEnumValue no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-28_

A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.

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
<td><p>valueid</p></td>
<td><p>smallint, não nulo</p></td>
<td><p>ID do valor.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, não nulo</p></td>
<td><p>ID do atributo.</p></td>
</tr>
<tr class="odd">
<td><p>atributo AttributeValue</p></td>
<td><p>nvarchar (256), não nulo</p></td>
<td><p>Nome do valor.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Chaves

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
<td><p>valueid</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>Valores da tabela

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueid</th>
<th>attributeID</th>
<th>atributo AttributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>1 </p></td>
<td><p>privada</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>1 </p></td>
<td><p>escopo</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>2 </p></td>
<td><p>SS</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>2 </p></td>
<td><p>Auditório</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>1 </p></td>
<td><p>Abre</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Confira também


[tblNode no Lync Server 2013](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

