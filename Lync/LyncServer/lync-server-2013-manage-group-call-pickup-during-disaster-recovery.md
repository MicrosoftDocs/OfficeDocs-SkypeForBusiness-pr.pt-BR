---
title: 'Lync Server 2013: gerenciar a coleta de chamadas em grupo durante a recuperação de desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Gerenciar a coleta de chamadas em grupo durante a recuperação de desastres no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

Quando um pool de front-end fica indisponível devido a um incidente não planejado, o serviço falha no pool de backup. Durante o failover para o pool de backup, os usuários são redirecionados para o pool de backup e estão no modo de resiliência. Enquanto estiver no modo de resiliência, os usuários não poderão atender as chamadas de outros usuários ou fazer com que as chamadas sejam selecionadas por outros usuários. Quando o failover for concluído, os usuários poderão usar novamente o recurso de recebimento de chamadas em grupo normalmente.

Durante o failback para o pool primário, os usuários são redirecionados para o pool primário e são novamente no modo de resiliência. A funcionalidade de recebimento de chamada de grupo não estará disponível até que os usuários estejam fora do modo de resiliência.

Esta seção discute algumas considerações para o recebimento de chamadas em grupo durante a recuperação de desastres e também descreve a experiência do usuário.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Considerações sobre o recebimento de chamadas em grupo durante a recuperação de desastres

Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada executado no pool de backup para os números de grupo de recebimento de chamadas. Portanto, o suporte para o recebimento de chamadas em grupo durante a recuperação de desastres requer que o aplicativo parque de chamadas seja implantado e habilitado no pool primário e no pool de backup.

Os intervalos de números do recurso de chamada em grupo na tabela órbita do parque de chamadas devem ser redirecionados para o pool de backup após o término do processo de failover do pool de backup. Os intervalos de números devem ser redirecionados para o pool primário após a conclusão do processo de failback para o pool primário. Para redirecionar os intervalos de recebimento da chamada em grupo, use o cmdlet **set-CsCallParkOrbit** .

Se você implantar um novo pool com um nome de domínio totalmente qualificado (FQDN) diferente para substituir o pool primário, será necessário reatribuir todos os intervalos de número de retirada de chamada de grupo que foram associados ao pool primário ao FQDN do novo pool. Para reatribuir intervalos de números ao novo pool, você pode usar o cmdlet **set-CsCallParkOrbit** . Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Experiência de recebimento de chamadas em grupo durante falha de pool

A tabela a seguir resume a experiência de retirada de chamadas em grupo pelas fases da recuperação de desastres.

### <a name="user-experience-during-disaster-recovery"></a>Experiência do usuário durante a recuperação de desastres

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Estado da chamada</th>
<th>Failover para pool de backup</th>
<th>Failback para pool primário</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Novas chamadas</p></td>
<td><p><strong>Durante o processo de failover:</strong></p>
<ul>
<li><p>Retirada de chamadas em grupo não disponível para usuários no modo de resiliência</p></li>
</ul>
<p><strong>Após a conclusão do failover:</strong></p>
<ul>
<li><p>Retirada de chamadas em grupo disponível quando os usuários estiverem fora da resiliência e os intervalos de números de recebimento de chamadas em grupo forem redirecionados para o pool de backup</p></li>
</ul></td>
<td><p><strong>Durante o processo de failback:</strong></p>
<ul>
<li><p>Retirada de chamadas em grupo não disponível para usuários no modo de resiliência</p></li>
</ul>
<p><strong>Após concluir o failback:</strong></p>
<ul>
<li><p>Retirada de chamadas em grupo disponível quando os usuários estiverem fora da resiliência e os intervalos de números de recebimento de chamadas em grupo forem redirecionados para o pool primário</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas na fila de recebimento de chamadas em grupo</p></td>
<td><p><strong>Durante o processo de failover:</strong></p>
<ul>
<li><p>As chamadas na fila não podem ser atendidas por meio da retirada de chamadas em grupo.</p></li>
</ul>
<p><strong>Após a conclusão do failover:</strong></p>
<ul>
<li><p>Nenhuma chamada neste estado</p></li>
</ul></td>
<td><p><strong>Durante o processo de failback:</strong></p>
<ul>
<li><p>As chamadas na fila não podem ser atendidas por meio da retirada de chamadas em grupo.</p></li>
</ul>
<p><strong>Após concluir o failback:</strong></p>
<ul>
<li><p>As chamadas na fila não podem ser atendidas por meio da retirada de chamadas em grupo.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Chamada estabelecida</p></td>
<td><p><strong>Durante o processo de failover:</strong></p>
<ul>
<li><p>As chamadas permanecem conectadas</p></li>
</ul>
<p><strong>Após a conclusão do failover:</strong></p>
<ul>
<li><p>As chamadas permanecem conectadas</p></li>
</ul></td>
<td><p><strong>Durante o processo de failback:</strong></p>
<ul>
<li><p>As chamadas permanecem conectadas</p></li>
</ul>
<p><strong>Após concluir o failback:</strong></p>
<ul>
<li><p>As chamadas permanecem conectadas</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

