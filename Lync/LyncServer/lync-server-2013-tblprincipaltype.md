---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de18da521bd4dadc63d5be592009bd60b643e7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-12_

PrincipalType contém os tipos principais para categorizar o que está na tabela tblPrincipal.

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
<td><p>não nulo nvarchar (256)</p></td>
<td><p>Descrição do tipo.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, não vazio</p></td>
<td><p>True se o tipo corresponder às entidades que são usadas para fins internos.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, não nulo</p></td>
<td><p>True se o tipo for um tipo de usuário.</p></td>
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
<th>Role</th>
<th>Descrição</th>
<th>Usuário</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Entidade genérica sem um tipo conhecido. Não usado na tabela tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>duas</p></td>
<td><p>AnyUser</p></td>
<td><p>Entidade de segurança genérica do tipo de usuário. Não é usada na tabela tblPrincipal.</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>3D</p></td>
<td><p>AnyGroup</p></td>
<td><p>Entidade de segurança genérica com semântica de grupo. Não é usada na tabela tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>quatro</p></td>
<td><p>SystemUser</p></td>
<td><p>Principal usada internamente pelo servidor de chat persistente.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>0,5</p></td>
<td><p>Usuário</p></td>
<td><p>Usuário regular.</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>CC</p></td>
<td><p>Controlador de domínio dos serviços de domínio Active Directory.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>Group</p></td>
<td><p>Grupo de segurança do Active Directory.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>Folder</p></td>
<td><p>Unidade organizacional ou recipiente do Active Directory.</p></td>
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

