---
title: 'Lync Server 2013: experiência de estacionamento de chamadas durante falha do pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61913ba4ccee86047bbed4d6454988d37081f5a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Experiência de estacionamento de chamadas no Lync Server 2013 durante falha do pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-10_

Quando um pool de front-ends fica indisponível devido a um incidente não planejado, as chamadas que foram estacionadas, mas ainda não foram recuperadas, são desconectadas. Durante o failover para um pool de backup, os usuários são redirecionados ao pool de backup e estão no modo de resiliência. Enquanto estão no modo de resiliência, os usuários não podem estacionar chamadas, mas podem colocar chamadas em espera e transferi-las. Quando o failover estiver concluído, as chamadas podem novamente ser estacionadas e recuperadas normalmente. Durante o failback, os usuários não podem estacionar chamadas até saírem do modo de resiliência.

Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada implantado no pool de backup. Portanto, os usuários que são redirecionados para o pool de backup usam as configurações de estacionamento de chamadas configuradas para o aplicativo de estacionamento de chamada no pool de backup.

A tabela a seguir resume a experiência de estacionamento de chamada através das fases de recuperação de desastres.

### <a name="user-experience-during-disaster-recovery"></a>Experiência do usuário durante a recuperação de desastres

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado da chamada</th>
<th>Quando ocorre uma interrupção</th>
<th>Durante o failover</th>
<th>Durante o failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamada ainda não estacionada</p></td>
<td><p>A chamada permanece conectada, mas não pode ser estacionada.</p></td>
<td><ul>
<li><p>Durante o failover, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocadas em espera e transferidas.</p></li>
<li><p>Quando o failover é concluído, a chamada pode ser estacionada e recuperada.</p></li>
</ul></td>
<td><ul>
<li><p>Durante o failback, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocadas em espera e transferidas.</p></li>
<li><p>Quando o failback é concluído, a chamada pode ser estacionada e recuperada.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamada estacionada, mas ainda não recuperada</p></td>
<td><p>A chamada é desconectada.</p></td>
<td><p>Nenhuma chamada neste estado.</p></td>
<td><p>A chamada é mantida estacionada.</p></td>
</tr>
<tr class="odd">
<td><p>Chamada estacionada já recuperada.</p></td>
<td><p>A chamada é mantida conectada.</p></td>
<td><p>A chamada é mantida conectada.</p></td>
<td><p>A chamada é mantida conectada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

