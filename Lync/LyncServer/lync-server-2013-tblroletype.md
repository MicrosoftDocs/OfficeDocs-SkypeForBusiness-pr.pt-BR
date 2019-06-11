---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-25_

tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.

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
<td><p>rtypeID</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID do tipo de função.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Descrição do tipo de função. Há quatro funções disponíveis:</p>
<ul>
<li><p>Membro: membro da sala de chat</p></li>
<li><p>Manager: gerente da sala de chat</p></li>
<li><p>Encaixado: apresentador para uma sala de chat do Auditorium</p></li>
<li><p>Creator: pode criar salas de chat</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Conjunto de permissões para a função. Os bits usados são:</p>
<ul>
<li><p>2: verdadeiro se a função puder gerenciar nós.</p></li>
<li><p>4: verdadeiro se a função puder criar nós filhos.</p></li>
<li><p>7: verdadeiro se a função puder ingressar em uma sala de chat (ou salas de chat dos filhos de uma categoria).</p></li>
<li><p>8: verdadeiro se a função puder conversar em uma sala de chat (ou nas salas de chat dos filhos de uma categoria).</p></li>
<li><p>10: verdadeiro se a função puder ler o histórico de chats mesmo quando não estiver associado a uma sala de chat.</p></li>
<li><p>11: verdadeiro se a função puder ver a sala de chat. (Isso é ainda mais refinado por fatores como escopo e visibilidade.)</p></li>
<li><p>12: verdadeiro se a função puder conversar em uma sala de chat do Auditorium.</p></li>
<li><p>13: verdadeiro se a função puder ignorar as regras de visibilidade ao exibir nós.</p></li>
</ul></td>
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
<td><p>rtypeID</p></td>
<td><p>Chave primária.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

