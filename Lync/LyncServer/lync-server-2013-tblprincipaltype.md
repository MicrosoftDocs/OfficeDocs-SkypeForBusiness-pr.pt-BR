---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.

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
<td><p>ptypeID</p></td>
<td><p>smallint, não nulo</p></td>
<td><p>ID do tipo principal.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Descrição do tipo.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se o tipo corresponder às entidades de segurança usadas para fins internos.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se o tipo for um tipo de usuário.</p></td>
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
<td><p>ptypeID</p></td>
<td><p>Chave primária.</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>Valores principais

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Função</th>
<th>Descrição</th>
<th>Usuário</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Qualquer um</p></td>
<td><p>Entidade de segurança genérica sem tipo conhecido. Não usado na tabela tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>Entidade de usuário genérica do tipo de usuário. Não usado na tabela tblPrincipal.</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Entidade de segurança genérica com semântica de grupo. Não usado na tabela tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>Principal usado internamente pelo servidor de chat persistente.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>Usuário</p></td>
<td><p>Usuário regular.</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>08</p></td>
<td><p>CLONA</p></td>
<td><p>Controlador de domínio dos serviços de domínio Active Directory.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>222</p></td>
<td><p>Grupos</p></td>
<td><p>Grupo de segurança do Active Directory.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>254</p></td>
<td><p>La</p></td>
<td><p>Contêiner ou unidade organizacional do Active Directory.</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Confira também


[tblPrincipal no Lync Server 2013](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

