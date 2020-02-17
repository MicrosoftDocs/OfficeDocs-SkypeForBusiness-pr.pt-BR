---
title: 'Lync Server 2013: monitoramento de limites de capacidade de memória do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45600ed9c822851c89b13cb776bbc58464decde0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Monitoramento de limites de capacidade de memória do servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> As informações neste tópico referem-se ao planejamento de capacidade referem-se apenas aos clientes móveis do Lync 2010 e ao serviço de mobilidade (MCX). O planejamento de capacidade para a API da Web de comunicações unificadas (UCWA), usado pelos clientes móveis do Lync 2013, é fornecido pelo Lync Server 2013, ferramenta de planejamento.



</div>

Dois contadores de desempenho de mobilidade podem ajudá-lo a determinar o uso atual e a ajudá-lo a planejar a capacidade do Lync Server 2013 Mobility Service (MCX), bem como monitorar o uso de memória para o UCWA. Para o UCWA, a categoria de contador é **ls: Web – UCWA**. Para o serviço de mobilidade (MCX), os contadores estão sob a categoria **ls: Web-Mobile Communication Service**. Os contadores a serem monitorados são:

  - **Contagem de sessão ativa no momento com assinaturas de presença ativa**, que é o número atual de pontos de extremidade registrados através do UCWA ou do serviço de mobilidade (MCX) que possuem assinaturas de presença ativa (número de usuários móveis sempre conectados)

  - **Contagem de sessão ativa no momento**, que é o número atual de pontos de extremidade registrados através do UCWA ou do serviço de mobilidade

Se a diferença entre a **contagem de sessão ativa no momento com assinaturas de presença ativas** e a **contagem de sessão ativa no momento** for pequena ao longo do tempo, isso significa que a maioria dos usuários de dispositivos móveis têm um dispositivo sempre conectado, como um dispositivo móvel Android ou Nokia (apenas para MCX). Os dispositivos UCWA sempre conectados incluem dispositivos Apple e Android que executam clientes móveis do Lync 2013). Se a **contagem de sessão ativa no momento** for muito maior do que a contagem de sessões ativas **no momento com assinaturas de presença ativa**, isso indica que mais usuários estão usando um dispositivo de ponto de extremidade de segundo plano, como um dispositivo Apple Ios ou Windows Phone em MCX. (O Windows Phone é o único cliente móvel do Lync 2013 que será registrado como este).

Você deve definir um limite na **contagem de sessão ativa no momento com assinaturas de presença ativas** e contadores de desempenho de **contagem de sessão ativos atualmente** com base no uso esperado, nos resultados de planejamento de capacidade e no monitoramento contínuo do serviço de mobilidade e de outros contadores de servidor de front-end. Os limites definidos devem permitir que você avalie a capacidade do servidor e gere alertas quando a capacidade for excedida.

Para determinar os limites apropriados, você precisa primeiro determinar a quantidade de memória disponível no servidor front-end para o serviço de mobilidade. Monitore os contadores para determinar quando você precisa planejar capacidade extra, de acordo com a fórmula a seguir:

Memória total usada pelo serviço de mobilidade MCX (MB) = 164 + (400 + 134)/1024 \* **contagem de sessão ativa no momento com assinaturas de presença ativas** + 400 \* /1024 (contagem de sessão ativa**no** momento – **contagem de sessão ativa no momento com assinaturas de presença ativas**)

<div>


> [!IMPORTANT]  
> A calculadora de capacidade do Microsoft Lync Server 2010 é uma planilha preenchida previamente com todas as fórmulas que permitem que um planejador determine quais são os requisitos para os servidores, incluindo CPU, memória e disco rígido. Você pode baixar a planilha e um documento associado em:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

O servidor front-end precisa de memória suficiente disponível para suportar o serviço de mobilidade em situações de failover. Você pode monitorar a memória atual disponível no servidor front-end usando o contador **memória\\disponível de Mbytes** ou usando a equação mencionada anteriormente para planejar a quantidade de memória que você espera que o serviço de mobilidade use.

Se a quantidade de memória disponível no servidor front-end for inferior a 1.500 MB quando você planejar o número esperado de usuários de mobilidade, você precisará adicionar mais hardware para dar suporte ao serviço de mobilidade. Para obter mais detalhes, consulte [Monitoring Mobility for Performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) na documentação operações.

<div>

## <a name="see-also"></a>Confira Também


[Monitorando a mobilidade para desempenho no Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

