---
title: 'Lync Server 2013: considerações de interoperabilidade para videoconferência'
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
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Considerações de interoperabilidade para videoconferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Esta seção descreve a experiência do usuário durante a fase de coexistência da migração, quando há interoperabilidade entre clientes herdados e um pool do Lync Server 2013 ou clientes do Lync Server 2013 e um pool herdado.

<div>

## <a name="lync-server-2013-pools"></a>Pools do Lync Server 2013

Os usuários perceberão o seguinte comportamento quando um cliente herdado for usado em um pool do Lync Server 2013:

  - Para chamadas de dois participantes, a resolução de vídeo é a mesma do pool herdado.

  - Para conferências com vários participantes, a resolução de vídeo e os recursos de videoconferência são iguais aos do pool herdado. O modo de exibição de galeria e alta resolução não estão disponíveis.

</div>

<div>

## <a name="legacy-pools"></a>Pools herdados

Os usuários perceberão o seguinte comportamento quando um cliente do Lync Server 2013 for usado em um pool herdado:

  - Para chamadas de dois participantes, os clientes do Lync Server 2013 podem usar novos recursos da seguinte maneira:
    
      - H. 264 estará disponível se ambos os participantes estiverem usando os clientes do Lync Server 2013.
    
      - O cliente do Lync Server 2013 usa o valor padrão para TotalReceiveVideoBitRateKb, uma vez que o servidor herdado não envia essas informações com o provisionamento em banda.

  - Para conferências com vários participantes, a resolução de vídeo e os recursos de videoconferência são os mesmos que um cliente herdado no pool herdado.

<div>


> [!NOTE]  
> Quando um servidor herdado hospeda um cliente do Lync Server 2013, é possível configurar a largura de banda de videoconferência para que todos os usuários do pool recebam somente vídeo de baixa resolução, mas enviem vídeo de alta resolução. Um exemplo disso é quando MaxVideoRateAllowed está definido como CIF-250K na configuração de mídia e VideoBitRateKb é definido como 2000 kbps na política de conferência. Nesse caso, o efeito de alta resolução não é possível para os usuários do pool.<BR>Como o MaxVideoRateAllowed não é mais usado para clientes do Lync Server 2013, ele não pode impedir que os clientes do Lync Server 2013 solicitem vídeo de alta resolução. Em vez disso, defina VideoBitRateKb na política de conferência para todos os usuários no pool para o mesmo valor que MaxVideoRateAllowed (ou seja, CIF é definido como 250 kbps ou VGA está definido como 600 kbps ou HD é definido como 1500 kbps).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

