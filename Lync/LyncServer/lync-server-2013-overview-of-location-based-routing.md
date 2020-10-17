---
title: 'Lync Server 2013: visão geral do roteamento de Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48fee2b9db45519ff4773b4dfe47b33745e5fb10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520958"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Visão geral do roteamento de Location-Based no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

O roteamento de Location-Based introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para impedir o desvio de chamada. Location-Based roteamento fornece a flexibilidade para definir o escopo dessas regras para regiões específicas, gateways específicos ou apenas para o conjunto específico de usuários.

Os cenários a seguir ilustram os principais tipos de restrições Location-Based o roteamento pode impor:

  - Chamadas de egresso – o roteamento Location-Based pode impor chamadas de saída para saída de um gateway PSTN localizado na mesma região em que o chamador deve impedir o bypass de chamada PSTN, o que impede chamadas de saída de um gateway PSTN localizado em uma região diferente como o chamador.

  - Chamadas de ingresso – Location-Based roteamento pode impedir chamadas PSTN de entrada para apontar pontos de extremidade do Lync se o gateway PSTN que está encaminhando a chamada de entrada não está localizado na mesma região que o usuário chamado do Lync.

  - Regiões desconhecidas – Location-Based roteamento restringe as chamadas PSTN de entrada e saída para e de usuários localizados em locais indeterminados (ou seja, usuários remotos que se conectam a partir da Internet ou localizados em regiões desconhecidas).

  - Regiões internacionais – Location-Based roteamento aplica o roteamento de chamadas de saída por meio de gateways PSTN internacionais se não for possível encontrar um gateway local para o local do usuário.

<div>

## <a name="see-also"></a>Confira também


[Planejamento de roteamento de Location-Based no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

