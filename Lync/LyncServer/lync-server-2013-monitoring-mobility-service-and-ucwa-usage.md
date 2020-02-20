---
title: 'Lync Server 2013: monitorando o serviço de mobilidade e o uso do UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94a04e310e3d7c7d0954ba8a34088a41d1692df8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Monitorando o serviço de mobilidade e o uso do UCWA no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-14_

Em uma base contínua, você deve monitorar a CPU e a memória que é usada pelo Lync Server Mobility Service (MCX) e pela API Web de comunicações unificadas (UCWA). Para monitorar o uso, você pode usar o seguinte:

**Para a API Web de comunicações unificadas (UCWA):**

  - O processo de trabalho do **LyncUcwa** no Gerenciador de serviços de informações da Internet (IIS). No painel **processos de trabalho** , examine as colunas **CPU%** e **bytes particulares (KB)** (memória).

  - Os contadores de desempenho **da CPU** e do **processador** .

Para a maioria das implantações, o uso da CPU do UCWA deve estar abaixo de 15% em média. O uso de memória deve ficar dentro dos limites descritos em [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:

  - **Ls: Web – limitação e Web\\de autenticação – total de solicitações em processamento**, que indica o número de solicitações da Web pendentes no servidor. Quando esse contador chegar a 10.000, as solicitações subsequentes falharão, com a mensagem de erro "503-Serviço indisponível".

  - **Solicitações\\ASP.NET Enfileiradas** (devem sempre ser zero).

<div>


> [!NOTE]  
> Se você atender ou exceder esses valores, deverá revisitar e recalcular seu planejamento de capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.



</div>

**Para o serviço de mobilidade (MCX):**

  - Os processos de trabalho do **CSIntMcxAppPool** e do **CSExtMcxAppPool** no Gerenciador de serviços de informações da Internet (IIS). No painel **processos de trabalho** , examine as colunas **CPU%** e **bytes particulares (KB)** (memória).

  - Os contadores de desempenho **da CPU** e do **processador** .

Para a maioria das implantações, o uso da CPU do serviço de mobilidade deve estar abaixo de 15%, em média. O uso de memória deve ficar dentro dos limites descritos em [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho do ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:

  - **ASP.NET v 2.0.50727\\solicitações atuais**, que indica o número de solicitações pendentes da Web no servidor. Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com a mensagem de erro "503-Serviço indisponível".

  - **Solicitações\\ASP.NET Enfileiradas** (devem sempre ser zero).

<div>


> [!NOTE]  
> Se você atender ou exceder esses valores, deverá revisitar e recalcular seu planejamento de capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.



</div>

<div>

## <a name="see-also"></a>Confira também


[Monitoramento de limites de capacidade de memória do servidor no Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

