---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1b5096c087661bf5afadd2668d6d1bb7ac8330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>tblADCookie no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-25_

tblADCookie contém os atuais cookies de sincronização de LDAP (Lightweight Directory Access Protocol).

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
<td><p>GUID principal do domínio que está sendo monitorado.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>FQDN (nome de domínio totalmente qualificado) do controlador de domínio atual usado para a sincronização dos serviços de domínio Active Directory. Tem valor informativo.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>imagem (binário)</p></td>
<td><p>Cookie de sincronização do Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>Carimbo de data/hora com o tempo de atualização de linha.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>Tempo até que a linha esteja bloqueada para alterações. Isso faz parte de um mecanismo de travamento do software que garante que apenas um dos serviços de chat faça a sincronização do Active Directory de cada vez.</p></td>
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
<th>Coluna (s)</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Chave estrangeira com pesquisa na tabela principal. prinGuid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

