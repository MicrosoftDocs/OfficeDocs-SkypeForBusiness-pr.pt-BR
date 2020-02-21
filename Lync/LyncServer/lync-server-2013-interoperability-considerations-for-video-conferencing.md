---
title: 'Lync Server 2013: considerações de interoperabilidade para conferência de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6157b9dc8867b2f458eafb6f0343fd43a19af537
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Considerações de interoperabilidade para conferência de vídeo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Esta seção descreve a experiência do usuário durante a fase de coexistência da migração, quando há interoperabilidade entre clientes herdados e um pool do Lync Server 2013 ou clientes do Lync Server 2013 e um pool herdado.

<div>

## <a name="lync-server-2013-pools"></a>Pools do Lync Server 2013

Os usuários perceberão o seguinte comportamento quando um cliente herdado for usado em um pool do Lync Server 2013:

  - Para chamadas de duas partes, a resolução de vídeo é a mesma da resolução do pool herdado.

  - Para conferências com vários participantes, os recursos de resolução de vídeo e videoconferência são os mesmos dos presentes no pool herdado. O modo de exibição de galeria e a alta resolução não estão disponíveis.

</div>

<div>

## <a name="legacy-pools"></a>Pools herdados

Os usuários experimentarão o seguinte comportamento quando um cliente do Lync Server 2013 for usado em um pool herdado:

  - Para chamadas de duas partes, os clientes do Lync Server 2013 podem usar os novos recursos da seguinte maneira:
    
      - H. 264 estará disponível se ambos os participantes estiverem usando os clientes do Lync Server 2013.
    
      - O cliente do Lync Server 2013 usa o valor padrão para TotalReceiveVideoBitRateKb, já que o servidor herdado não envia essas informações com o provisionamento em banda.

  - Para conferências com vários participantes, os recursos de resolução de vídeo e videoconferência são os mesmos observados por um cliente herdado no pool herdado.

<div>


> [!NOTE]  
> Quando um servidor herdado hospeda um cliente do Lync Server 2013, é possível configurar a largura de banda de audioconferência para que todos os usuários do pool recebam apenas vídeo de baixa resolução, mas enviem vídeo de alta resolução. Um exemplo disso é quando MaxVideoRateAllowed é definido como CIF-250K na configuração de mídia e VideoBitRateKb é definido como 2.000 kbps na política de conferências. O efeito líquido dessa situação é que uma alta resolução não é possível para os usuários no pool.<BR>Como o MaxVideoRateAllowed não é mais usado para clientes do Lync Server 2013, ele não pode impedir que os clientes do Lync Server 2013 solicitem vídeo de alta resolução. Em vez disso, defina VideoBitRateKb na política de conferências para todos os usuários do pool como o mesmo valor de MaxVideoRateAllowed (isto é, CIF é definido como 250 kbps, VGA é definido como 600 kbps ou HD é definido como 1.500 kbps).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

