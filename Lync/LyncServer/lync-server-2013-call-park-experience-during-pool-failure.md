---
title: 'Lync Server 2013: Experiência de Estacionamento de Chamadas durante falha de pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>Experiência de Estacionamento de Chamadas no Lync Server 2013 durante falha de pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-10_

Quando um pool de front-end fica indisponível devido a um incidente não planejado, as chamadas que foram estacionadas, mas que ainda não foram recuperadas, são desconectadas. Durante o failover para um pool de backup, os usuários são redirecionados para o pool de backup e estão no modo de resiliência. Enquanto estiver no modo de resiliência, os usuários não podem estacionar chamadas, mas podem fazer chamadas em espera e transferi-las. Quando o failover é concluído, as chamadas podem ser novamente estacionadas e recuperadas normalmente. Durante o failback, os usuários não podem estacionar chamadas até que estejam fora do modo de resiliência.

Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada que é implantado no pool de backup. Portanto, os usuários que são redirecionados para o pool de backup usam as configurações de estacionamento de chamadas configuradas para o aplicativo de estacionamento de chamadas no pool de backup.

A tabela a seguir resume a experiência de estacionamento de chamadas pelas fases da recuperação de desastres.

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
<th>Quando ocorrer uma paralisação</th>
<th>Durante o failover</th>
<th>Durante o failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamada ainda não estacionada</p></td>
<td><p>A chamada ainda está conectada, mas não pode ser estacionada.</p></td>
<td><ul>
<li><p>Durante o failover, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocados em espera e transferidos.</p></li>
<li><p>Quando o failover é concluído, a chamada pode ser estacionada e recuperada.</p></li>
</ul></td>
<td><ul>
<li><p>Durante o failback, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocados em espera e transferidos.</p></li>
<li><p>Quando o failback é concluído, a chamada pode ser estacionada e recuperada.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamada estacionada, mas ainda não recuperada</p></td>
<td><p>A chamada está desconectada.</p></td>
<td><p>Não há chamadas nesse estado.</p></td>
<td><p>A chamada permanece estacionada.</p></td>
</tr>
<tr class="odd">
<td><p>Chamada estacionada já recuperada</p></td>
<td><p>A chamada permanecerá conectada.</p></td>
<td><p>A chamada permanecerá conectada.</p></td>
<td><p>A chamada permanecerá conectada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

