---
title: 'Lync Server 2013: tblRoleType'
description: 'Lync Server 2013: tblRoleType.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f458259acaee7821d5f6a7339b993c70fe65f595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568537"
---
# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-25_

tblRoleType é uma tabela de pesquisa estática com tipos de funções e seus conjuntos de permissões associados.

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
<td><p>int, not null</p></td>
<td><p>ID do tipo de função.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Descrição do tipo de função. Existem quatro funções disponíveis:</p>
<ul>
<li><p>Membro: Membro da sala de chat</p></li>
<li><p>Gerente: Gerente da sala de chat</p></li>
<li><p>Com voz: Apresentador para uma sala de chat de auditório</p></li>
<li><p>Criador: Pode criar salas de bate-papo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, not null</p></td>
<td><p>Permissão configurada para a função. Os bits usados são:</p>
<ul>
<li><p>2: True se a função puder gerenciar nós.</p></li>
<li><p>4: True se a função puder criar nós filhos.</p></li>
<li><p>7: True se a função puder entrar em uma sala de chat (ou nas salas filhos de uma categoria).</p></li>
<li><p>8: True se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria).</p></li>
<li><p>10: True se a função puder ler o histórico do chat mesmo quando não tiver entrado na sala de chat.</p></li>
<li><p>11: True se a função puder ver a sala de chat (refinado por fatores como escopo e visibilidade).</p></li>
<li><p>12: True se a função puder conversar em uma sala de chat de auditório.</p></li>
<li><p>13: True se a função puder ignorar as regras de visibilidade ao exibir nós.</p></li>
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

