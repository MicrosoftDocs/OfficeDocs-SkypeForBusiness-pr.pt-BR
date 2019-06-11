---
title: 'Lync Server 2013: monitoramento de limites de capacidade de memória do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68728c85b14231644b445569857896f34abe535f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Monitorar os limites de capacidade de memória do servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> As informações neste tópico referem-se ao planejamento da capacidade refere-se somente aos clientes móveis do Lync 2010 e ao serviço de mobilidade (MCX). O planejamento de capacidade para a API da Web de comunicação unificada (UCWA), usado pelos clientes móveis do Lync 2013, é fornecido pela ferramenta de planejamento 2013 do Lync Server.



</div>

Dois contadores de desempenho de mobilidade podem ajudar você a determinar o uso atual e a ajudá-lo a planejar a capacidade do serviço de mobilidade do Lync Server 2013 (MCX), bem como monitorar o uso da memória para UCWA. No caso da UCWA, a categoria do contador é **LS:WEB – UCWA**. Para o Serviço de mobilidade (Mcx), os contadores estão sob a categoria **LS:WEB - Mobile Communication Service**. Os contadores para monitoramento são:

  - **Contagem atual da sessão ativa com as assinaturas de presença ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de mobilidade ou UCWA que tem assinaturas de presença ativa (número de usuários móveis sempre conectados).

  - **Contagem atual de sessão ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de Mobilidade ou UCWA.

Se a diferença entre **Contagem atual de sessão ativa com assinaturas de presença ativa** e **Contagem atual de sessão ativa** for pequena com o passar do tempo, isso significa que a maioria dos usuários de dispositivos móveis tem um dispositivo sempre conectado, como um dispositivo Android ou Nokia (somente para Mcx). Os dispositivos UCWA sempre conectados incluem dispositivos Apple e Android que executam clientes móveis do Lync 2013). Se **Contagem atual de sessão ativa** for muito maior que **Contagem atual de sessão ativa com assinaturas de presença ativa**, isso mostra que mais usuários estão usando um dispositivo de ponto de extremidade de plano de fundo, como um dispositivo Apple iOS ou um Windows Phone com Mcx. (O Windows Phone é o único cliente móvel do Lync 2013 que será registrado como este).

Você deve definir um limite na **contagem de sessões ativas atualmente com assinaturas de presença ativas** e contadores de desempenho de **contagem de sessões ativas no momento** com base no uso esperado, nos resultados de planejamento de capacidade e na monitoração contínua de Serviço de mobilidade e outros contadores de servidor front-end. Os limites que você definir devem permitir a avaliação da capacidade do servidor e emitir alertas quando a capacidade for excedida.

Para determinar os limites apropriados, você precisa primeiro determinar a quantidade de memória disponível no servidor front-end para o serviço de mobilidade. Monitore os contadores determinar quando você precisa planejar uma capacidade extra, de acordo com a fórmula a seguir:

Total de memória usada pelo serviço de mobilidade do MCX (MB) = 164 + (400 + 134) \* /1024 **contagem de sessões ativas atualmente com assinaturas de presença** ativas \* + 400/1024 (**contagem de sessões ativas** no **momento – contagem de sessões ativas atualmente com assinaturas de presença ativas**)

<div>


> [!IMPORTANT]  
> A calculadora de capacidade do Microsoft Lync Server 2010 é uma planilha preenchida previamente com todas as fórmulas que permitem ao Planner determinar quais são os requisitos para os servidores, incluindo CPU, memória e disco rígido. Você pode baixar a planilha e um documento associado em:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

O servidor front-end precisa de memória suficiente disponível para dar suporte ao serviço de mobilidade em situações de failover. Você pode monitorar a memória atual disponível no servidor front-end usando o contador **memória\\disponível** em Mbytes ou usando a equação mencionada anteriormente, para planejar a quantidade de memória que você espera que o serviço de mobilidade use.

Se a quantidade de memória disponível no servidor front-end for inferior a 1.500 MB ao planejar o número esperado de usuários da mobilidade, você precisará adicionar mais hardware para dar suporte ao serviço de mobilidade. Para obter mais detalhes, consulte Monitorando a [mobilidade para desempenho no Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) na documentação de operações.

<div>

## <a name="see-also"></a>Confira também


[Monitorando a mobilidade para o desempenho no Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

