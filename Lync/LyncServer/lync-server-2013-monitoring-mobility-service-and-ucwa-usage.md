---
title: 'Lync Server 2013: monitorar o serviço de mobilidade e o uso do UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Monitorar o serviço de mobilidade e o uso do UCWA no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-14_

Continuamente, você deve monitorar a CPU e a memória usadas pelo Lync Server Mobility Service (MCX) e pela API Web de comunicação unificada (UCWA). Para monitorar o uso, você pode usar uma das opções a seguir:

**Para Unified Communications Web API (UCWA):**

  - O processo de trabalho do **LyncUcwa** no Gerenciador dos serviços de informações da Internet (IIS). No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.

  - Os contadores de desempenho da **CPU** e do **Processador**.

Na maioria das implantações, o uso da CPU do UWCA deve estar abaixo de 15%, em média. O uso da memória deve ficar dentro dos limites descritos em [monitoramento para limites de capacidade de memória do servidor no Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:

  - **Ls: Web – Web-throttling\\e autenticação – total de solicitações em processamento**, que indica o número de solicitações pendentes da Web no servidor. Quando esse contador chegar a 10.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".

  - **Solicitações\\ASP.net** enfileiradas (sempre deve ser zero).

<div>


> [!NOTE]  
> Se você atender ou ultrapassar esses valores, consulte novamente e recalcule o planejamento de capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.



</div>

**Para o Mobility Service (Mcx):**

  - Os processos de trabalho do **CSIntMcxAppPool** e do **CSExtMcxAppPool** no Gerenciador dos serviços de informações da Internet (IIS). No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.

  - Os contadores de desempenho da **CPU** e do **Processador**.

Na maioria das implantações o uso da CPU do Mobility Service deve estar abaixo de 15%, em média. O uso da memória deve ficar dentro dos limites descritos em [monitoramento para limites de capacidade de memória do servidor no Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:

  - O **ASP.NET v\\2.0.50727 requests Current**, que indica o número de solicitações pendentes da Web no servidor. Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".

  - **Solicitações\\ASP.net** enfileiradas (sempre deve ser zero).

<div>


> [!NOTE]  
> Se você satisfaz ou supera esses valores, deve revisitar e recalcular o planejamento da capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.



</div>

<div>

## <a name="see-also"></a>Confira também


[Monitorar os limites de capacidade de memória do servidor no Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

