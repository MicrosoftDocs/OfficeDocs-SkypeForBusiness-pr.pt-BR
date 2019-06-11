---
title: 'Lync Server 2013: visão geral do roteamento baseado em local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Visão geral do roteamento baseado em local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

O roteamento baseado na localização introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para evitar desvio de tarifas. O roteamento baseado na localização oferece a flexibilidade para abranger essas regras em regiões específicas, gateways específicos ou somente conjunto de usuários específico.

Os cenários a seguir ilustram os principais tipos de restrições de roteamento baseado em local que podem ser forçadas:

  - Chamadas de egresso – o roteamento baseado em local pode impor chamadas feitas para egresso a partir de um gateway PSTN localizado na mesma região onde o chamador é para impedir o bypass de chamada PSTN, o que impede chamadas para egresso de um gateway PSTN localizado em uma região diferente do externo.

  - Chamadas de ingresso – o roteamento baseado em local pode impedir chamadas PSTN de entrada para pontos de extremidade do Lync, se o gateway PSTN que faz a chamada de entrada não estiver localizado na mesma região que o usuário chamado do Lync.

  - Regiões desconhecidas – o roteamento baseado em local restringe as chamadas PSTN de entrada e saída para e de usuários localizados em locais indeterminados (ou seja, usuários remotos que se conectam pela Internet ou localizados em regiões desconhecidas).

  - Regiões internacionais – o roteamento baseado em local obriga o roteamento de chamadas feitas por meio de gateways PSTN internacionais se um gateway local para o local do usuário não puder ser encontrado.

<div>

## <a name="see-also"></a>Confira também


[Planejamento de Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

