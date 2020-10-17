---
title: 'Lync Server 2013: Delegação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b31224228a4f2fbdad879e43bab61292852e009c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516298"
---
# <a name="delegation-in-lync-server-2013"></a>Delegação no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

Os recursos de delegação no Lync são afetados pelo roteamento Location-Based da seguinte maneira:

  - Quando um representante habilitado para Location-Based roteamento coloca uma chamada em nome de um gerente, a política de voz do representante é usada para autorizar a chamada e a política de roteamento de voz do site do representante será usada para encaminhar a chamada

  - Para chamadas PSTN de entrada para um gerente, as mesmas regras aplicáveis ao encaminhamento de chamadas ou ao toque simultâneo serão aplicadas conforme descrito nos tópicos de transferências de chamada e de encaminhamento e toque simultâneo.

  - Quando um representante define um ponto de extremidade PSTN como um alvo de anel simultâneo, para uma chamada de entrada para o gerente, a política de roteamento de voz do site que está associado ao tronco de entrada será usada para rotear a chamada para o ponto de extremidade PSTN do representante.

  - Para delegação, é recomendável que o gerente e seus representantes associados estejam geralmente localizados no mesmo local de rede.

<div>

## <a name="see-also"></a>Confira também


[Cenários para Location-Based roteamento no Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

