---
title: 'Lync Server 2013: visão geral do roteamento baseado em local'
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
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Visão geral do roteamento baseado em local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

O roteamento baseado em local introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para evitar o desvio de chamada. O roteamento baseado em local oferece a flexibilidade para definir o escopo dessas regras para regiões específicas, gateways específicos ou apenas para o conjunto específico de usuários.

Os cenários a seguir ilustram os principais tipos de restrições que o roteamento baseado em local pode impor:

  - Chamadas de egresso – o roteamento baseado em local pode impor chamadas de saída para saída de um gateway PSTN localizado na mesma região em que o chamador deve impedir o bypass de interrupções PSTN, o que impede chamadas de saída de um gateway PSTN localizado em uma região diferente como pelas.

  - Chamadas de ingresso – o roteamento baseado em local pode impedir chamadas PSTN de entrada para apontar pontos de extremidade do Lync, se o gateway PSTN que estiver encaminhando a chamada de entrada não estiver localizado na mesma região do usuário chamado Lync.

  - Regiões desconhecidas – o roteamento baseado em local restringe as chamadas PSTN de entrada e saída para e de usuários localizados em locais indeterminados (ou seja, usuários remotos que se conectam a partir da Internet ou localizados em regiões desconhecidas).

  - Regiões internacionais – o roteamento baseado em local impõe o roteamento de chamadas de saída por meio de gateways PSTN internacionais se não for possível encontrar um gateway local para o local do usuário.

<div>

## <a name="see-also"></a>Confira também


[Planejamento de roteamento baseado em local no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

