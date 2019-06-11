---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.

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
<td><p>prinGuid</p></td>
<td><p>GUID, não nulo</p></td>
<td><p>GUID principal. Isso é amplamente usado como uma chave primária alternativa porque o significado é cruzado para o espaço dos serviços de domínio Active Directory. (O GUID de uma entidade do cache é igual à GUID do objeto do Active Directory correspondente.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>URI principal. O esquema SIP é usado para os usuários, e o ma-GRP é usado para praticamente tudo o mais.</p></td>
</tr>
<tr class="even">
<td><p>imprimir</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome comum. Usado apenas por tipos de usuário.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Nome para exibição. Usado apenas por tipos de usuário.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome da empresa. Usado apenas por tipos de usuário.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Email. Usado apenas por tipos de usuário.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Nome do domínio do objeto do Active Directory que a entidade de segurança é uma versão em cache de. Pode ser NULL para tipos que não sejam objetos do Active Directory (como usuários do sistema).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome UPN do usuário. Usado apenas por tipos de usuário regulares.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, não nulo</p></td>
<td><ul>
<li><p>0: a entidade de segurança está ativa.</p></li>
<li><p>1: o principal está desabilitado porque as funcionalidades SIP do usuário estão desabilitadas.</p></li>
<li><p>2: o principal é excluído porque o objeto do anúncio associado foi excluído.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, não nulo</p></td>
<td><p>Tipo de entidade de segurança (da tabela tblPrincipalType).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Núm</p></td>
<td><p>Atribuição de pool do Lync para a entidade de segurança.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Núm</p></td>
<td><p>Valor da política do servidor de chat persistente para o usuário, se a política de tipo de marca estiver presente.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>ID da entidade de segurança do criador.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Carimbo de data/hora para a hora da criação.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>ID da entidade de segurança que atualizou pela última vez.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Carimbo de data/hora para a última atualização.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>DateTime, não nulo</p></td>
<td><p>Data e hora da última atualização de sincronização do Active Directory para a entidade de segurança.</p></td>
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
<td><p>multiimprimir</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblPrincipalType. ptypeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

