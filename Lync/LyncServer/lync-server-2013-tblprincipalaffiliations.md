---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>tblPrincipalAffiliations no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio Active Directory, em contêineres do Active Directory, em domínios.

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
<td><p>entidade de segurança</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID do objeto associado.</p></td>
</tr>
<tr class="even">
<td><p>afiliaid</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança que representa a afiliada. Cada entidade de segurança (exceto tipos de usuário do sistema) também tem uma afiliada.</p></td>
</tr>
<tr class="odd">
<td><p>dedo</p></td>
<td><p>int, não nulo</p></td>
<td><p>Dedo. O valor para autoafiliações é-1 e para as outras afiliações que ele aumenta sequencialmente de 1 dentro de cada &lt;objeto de entidade de segurança&gt; , o BucketID.</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int, não nulo</p></td>
<td><p>Entidade de segurança que fez a atualização mais recente. Geralmente, isso é 1, o que significa sincronização do Active Directory.</p></td>
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
<th>Colunas</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;entidade de segurança, índice, afiliaid&gt;</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>entidade de segurança</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</p></td>
</tr>
<tr class="odd">
<td><p>afiliaid</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

