---
title: 'Lync Server 2013: práticas recomendadas para controle de admissão de chamadas'
description: 'Lync Server 2013: práticas recomendadas para controle de admissão de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c32af904dc7fb48a1a5d1903bd6ed1f81f4cb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552127"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Práticas recomendadas para controle de admissão de chamadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-22_

Para aprimorar o desempenho e facilitar a implantação, aplique as práticas recomendadas a seguir quando implantar o controle de admissão de chamadas:

  - Garanta que as WANs estejam adequadamente provisionadas para o tráfego de mídia atual e antecipado.
    
    <div>
    

    > [!NOTE]  
    > É recomendável que você leve em consideração um buffer para seus limites de largura de banda. Existem cenários como condições de corrida que afetam a largura de banda total usada e podem resultar em situações em que o limite da largura de banda é excedido. Por exemplo, se duas chamadas tentarem iniciar enquanto o tráfego de mídia está alcançando um limite da largura de banda, uma delas pode ser recusada porque a outra conseguiu iniciar primeiro.

    
    </div>

  - Monitore o uso da rede e registros de detalhes de chamadas para que possa escolher configurações de CAC ótimas e atualizá-las conforme o uso da rede muda.

  - Use políticas de largura de banda de CAC para complementar as configurações de QoS.

  - Se você desejar rerotear chamadas bloqueadas para o PSTN, verifique a funcionalidade e a capacidade do PSTN. Para obter detalhes, consulte [Planning Outbound Voice Routing in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > A capacidade refere-se ao número de portas que precisam ser abertas para oferecer suporte a um possível reroteamento do PSTN.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

