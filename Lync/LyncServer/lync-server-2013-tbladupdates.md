---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a>tblADUpdates no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

o tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.

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
<td><p>prinGuid</p></td>
<td><p>GUID, não nulo</p></td>
<td><p>O principal GUID do objeto que foi alterado.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384), NOT NULL</p></td>
<td><p>Nome diferenciado do objeto.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>True se pelo menos um atributo do objeto foi alterado.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se a associação for alterada.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Não usado.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se o objeto foi excluído.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>DateTime, não nulo</p></td>
<td><p>Carimbo de data/hora de quando a linha foi inserida.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

