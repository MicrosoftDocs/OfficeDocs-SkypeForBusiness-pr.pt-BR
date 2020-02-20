---
title: 'Lync Server 2013: alterações feitas pela preparação do domínio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Alterações feitas pela preparação do domínio no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2010-10-18_

A tabela a seguir lista as ACEs (entradas de controle de acesso) que a preparação de domínio cria na raiz do domínio. Todas as ACEs serão herdadas, salvo indicação em contrário.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>ACEs adicionadas à raiz do domínio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-userreadonly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-useradmins</th>
<th>RTCHSUniversal-serviços</th>
<th>Usuários autenticados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ler contêiner (não herdado)</p></td>
<td><p>Sim</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Ler User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Ler User PropertySet Personal-Information</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Ler User PropertySet General-Information</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Ler User PropertySet Public-Information</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Ler User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Ler User PropertySet RTCPropertySet</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Gravar User Property Proxy-Addresses</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Gravar User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Gravar User PropertySet RTCPropertySet</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
</tr>
</tbody>
</table>


A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: Usuários, Computadores e Controladores de Domínio. Todas as ACEs são herdadas, a menos que especificado de outra forma.

### <a name="aces-added-to-built-in-containers"></a>ACEs adicionadas à contêineres internos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-userreadonly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ler contêiner (não herdado)</p></td>
<td><p>Sim</p></td>
<td><p><strong>Sim</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

