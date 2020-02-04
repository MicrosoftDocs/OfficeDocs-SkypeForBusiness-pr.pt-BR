---
title: 'Lync Server 2013: Tempo de recuperação para failover e failback de pool'
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
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Tempo de recuperação para failover e failback de pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-10_

Para failover de pool e failback de pool, o objetivo de engenharia do RTO do tempo de recuperação (RTO) é de 30 minutos. Esse é o tempo necessário para o failover acontecer, depois que os administradores determinaram que houve um desastre e iniciaram os procedimentos de failover. Isso não inclui o tempo para os administradores avaliarem a situação e tomarem uma decisão, nem inclui o tempo dos usuários entrarem novamente após o failover ser concluído.

Para failover de pool e failback de pool, o destino de engenharia do RPO (objetivo do ponto de recuperação) é de 30 minutos. Isso representa o tempo medido dos dados que pode ser perdido devido ao desastre, devido à latência de replicação do serviço de backup. Por exemplo, se um pool ficar inoperante às 10:00, e o RPO for de 30 minutos, os dados gravados no pool entre 9:30 A.M. e 10:00 A. M. talvez não tenham sido replicados para o pool de backup e seriam perdidos.

Todos os números de RTO e RPO neste documento supõem que os dois data centers estão localizados na mesma região do mundo com alta velocidade e transporte de baixa latência entre os dois locais. Esses números são medidos para um pool com 40.000 usuários ativos ao mesmo tempo e 200.000 usuários habilitados para Lync com respeito a um modelo de usuário predefinido, onde não há backlog na replicação de dados. Eles estão sujeitos a alteração baseado no teste e na validação de desempenho.

</div>

<span> </span>

</div>

</div>

</div>

