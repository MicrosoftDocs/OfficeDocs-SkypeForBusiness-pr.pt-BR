---
title: 'Lync Server 2013: gerenciar o recebimento de chamadas em grupo durante a recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 633ccf1c792f951d13c747c935af51569365c753
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Gerenciar o recebimento de chamadas em grupo durante a recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

Quando um pool de front-ends fica indisponível devido a um incidente não planejado, o serviço falha no pool de backup. Durante o failover para o pool de backup, os usuários são redirecionados para o pool de backup e estão no modo de resiliência. No modo de resiliência, os usuários não podem selecionar as chamadas de outros usuários ou fazer com que suas chamadas sejam escolhidas por outros usuários. Quando o failover é concluído, os usuários podem usar novamente o recebimento de chamadas em grupo como de costume.

Durante o failback para o pool primário, os usuários são redirecionados para o pool primário e estão novamente no modo de resiliência. A funcionalidade de recebimento de chamadas de grupo não está disponível até que os usuários estejam fora do modo de resiliência.

Esta seção discute algumas considerações para o recebimento de chamadas em grupo durante a recuperação de desastres e também descreve a experiência do usuário.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>Considerações sobre o recebimento de chamadas em grupo durante a recuperação de desastre

Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada em execução no pool de backup para os números do grupo de recebimento de chamada. Portanto, o suporte para o recebimento de chamadas em grupo durante a recuperação de desastres exige que o aplicativo de estacionamento de chamada seja implantado e habilitado no pool primário e no pool de backup.

Os intervalos de números de recebimento de chamadas de grupo na tabela de órbita de estacionamento de chamada devem ser redirecionados para o pool de backup após a conclusão do processo de failover para o pool de backup. Os intervalos de números devem ser redirecionados de volta para o pool primário após a conclusão do processo de failback para o pool primário. Para redirecionar os intervalos de recebimento de chamadas de grupo, use o cmdlet **set-CsCallParkOrbit** .

Se você implantar um novo pool com um FQDN (nome de domínio totalmente qualificado) diferente para substituir o pool primário, será necessário reatribuir todos os intervalos de número de recebimento de chamadas de grupo associados ao pool primário ao FQDN do novo pool. Para reatribuir intervalos de números ao novo pool, você pode usar o cmdlet **set-CsCallParkOrbit** . Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>Experiência de recebimento de chamadas de grupo durante falha do pool

A tabela a seguir resume a experiência de recebimento de chamadas de grupo por meio das fases de recuperação de desastres.

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
<li><p>Retirada de chamada em grupo não disponível para usuários no modo de resiliência</p></li>
</ul>
<p><strong>Após a conclusão do failover:</strong></p>
<ul>
<li><p>Retirada de chamada em grupo disponível quando os usuários são redirecionados para o pool de backup de resiliência e de chamada de grupo</p></li>
</ul></td>
<td><p><strong>Durante o processo de failback:</strong></p>
<ul>
<li><p>Retirada de chamada em grupo não disponível para usuários no modo de resiliência</p></li>
</ul>
<p><strong>Após a conclusão do failback:</strong></p>
<ul>
<li><p>Retirada de chamada em grupo disponível quando os usuários fora da resiliência e os intervalos de números de recebimento de chamadas de grupo são redirecionados de volta para o pool principal</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas na fila de recebimento de chamadas em grupo</p></td>
<td><p><strong>Durante o processo de failover:</strong></p>
<ul>
<li><p>As chamadas na fila não podem ser atendidas por recebimento de chamadas em grupo.</p></li>
</ul>
<p><strong>Após a conclusão do failover:</strong></p>
<ul>
<li><p>Nenhuma chamada neste estado</p></li>
</ul></td>
<td><p><strong>Durante o processo de failback:</strong></p>
<ul>
<li><p>As chamadas na fila não podem ser atendidas por recebimento de chamadas em grupo.</p></li>
</ul>
<p><strong>Após a conclusão do failback:</strong></p>
<ul>
<li><p>As chamadas na fila não podem ser atendidas por recebimento de chamadas em grupo.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Chamada estabelecida</p></td>
<td><p><strong>Durante o processo de failover:</strong></p>
<ul>
<li><p>Chamadas permanecem conectadas</p></li>
</ul>
<p><strong>Após a conclusão do failover:</strong></p>
<ul>
<li><p>Chamadas permanecem conectadas</p></li>
</ul></td>
<td><p><strong>Durante o processo de failback:</strong></p>
<ul>
<li><p>Chamadas permanecem conectadas</p></li>
</ul>
<p><strong>Após a conclusão do failback:</strong></p>
<ul>
<li><p>Chamadas permanecem conectadas</p></li>
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

