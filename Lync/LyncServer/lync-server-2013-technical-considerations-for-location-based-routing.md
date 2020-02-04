---
title: 'Lync Server 2013: Considerações técnicas para Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considerações técnicas para Roteamento Baseado em Local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-09_

Ao planejar o roteamento baseado em localização, considere o impacto para os cenários a seguir.

<div>

## <a name="disaster-recovery"></a>Recuperação de desastres

Durante um failover do pool primário para um pool de backup, bem como ao restaurar operações normais para o pool primário, o roteamento baseado em local permanecerá em vigor a qualquer momento durante um desastre e procedimento de recuperação.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Aparelho de Filial Persistente

Configurar o roteamento baseado em local impacta o planejamento de onde você implanta os gateways associados a seus aparelhos de ramificação sobreviventes. O gateway associado a seu SBA deve estar localizado no mesmo site de rede que o seu aparelho de ramificação sobreviventes; caso contrário, os usuários hospedados em seu aparelho de ramificação sobreviventes não terão permissão para fazer chamadas de saída se o roteamento baseado em localização estiver configurado. Quando a conexão WAN entre seu aparelho de ramificação sobreviventes e o site central está inativa, as restrições de roteamento baseadas em local permanecem impostas.

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

