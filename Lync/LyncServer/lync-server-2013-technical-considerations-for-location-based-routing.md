---
title: 'Lync Server 2013: considerações técnicas para roteamento de Location-Based'
description: 'Lync Server 2013: considerações técnicas para roteamento de Location-Based.'
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
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568047"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considerações técnicas para roteamento de Location-Based no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

Ao planejar Location-Based roteamento, considere o impacto nos cenários a seguir.

<div>

## <a name="disaster-recovery"></a>Recuperação de desastre

Durante um failover do pool primário para um pool de backup, bem como durante a restauração de operações normais para o pool primário, Location-Based roteamento permanecerá em vigor em todos os momentos durante um desastre e procedimento de recuperação.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Aplicativo de Filial Persistente

Configurar Location-Based o roteamento afeta o planejamento de onde você implanta os gateways associados a seus aparelhos de filial persistente. O gateway associado ao seu SBA deve estar localizado no mesmo local de rede que seu aparelho de filial persistente; caso contrário, os usuários hospedados no seu aparelho de filial persistente não terão permissão para fazer chamadas de saída se Location-Based roteamento estiver configurado. Quando a conexão WAN entre seu aparelho de filial persistente e o site central estiver inativa, Location-Based restrições de roteamento permanecerão impostas.

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de roteamento de Location-Based no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

