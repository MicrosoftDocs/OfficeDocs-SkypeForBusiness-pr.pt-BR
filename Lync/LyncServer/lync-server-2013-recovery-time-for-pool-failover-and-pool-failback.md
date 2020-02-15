---
title: Lync Server 2013 tempo de recuperação para failover de pool e failback de pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8692e01ed9691f69da7be78a2e0437e7829594cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Tempo de recuperação para failover de pool e failback de pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-10_

Para failover e failback de pool, o alvo projetado para objetivo de tempo de recuperação (RTO) é de 30 minutos. Este é o tempo necessário para o failover acontecer, após os administradores terem determinado que houve um desastre e iniciar os procedimentos de failover. Isso não inclui o tempo para os administradores avaliarem a situação e tomar uma decisão, nem inclui o tempo dos usuários entrarem novamente após o failover ser concluído.

Para failover e failback de pool, o alvo projetado para objetivo de tempo de recuperação (RTO) é de 30 minutos. Isso representa o tempo medido dos dados que pode ser perdido devido ao desastre, devido à latência de replicação do serviço de backup. Por exemplo, se um pool for desativado às 10:00 A.M., e o RPO for de 30 minutos, os dados gravados no pool entre 9:30 A.M. e 10:00 A. M. podem não ter sido replicados para o pool de backup e serão perdidos.

Todos os números de RTO e RPO neste documento supõem que os dois data centers estão localizados na mesma região com alta velocidade e trasporte de baixa latência entre os dois locais. Esses números são medidos para um pool com usuários simultâneos de 40.000 e 200.000 usuários habilitados para o Lync com relação a um modelo de usuário predefinido onde não há nenhuma lista de pendências na replicação de dados. Eles estão sujeitos à alteração baseado no teste e validação de desempenho.

</div>

<span> </span>

</div>

</div>

</div>

