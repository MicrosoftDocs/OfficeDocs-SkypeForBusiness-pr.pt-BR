---
title: 'Lync Server 2013: Configurando o serviço de mobilidade para alto desempenho'
description: 'Lync Server 2013: Configurando o serviço de mobilidade para alto desempenho.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4732d9f6a92c383a105a6f0d7162c9b6c798de24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556977"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Configurando o serviço de mobilidade para alto desempenho no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Este tópico se aplica apenas ao Lync Server 2013 Mobility Service (MCX) e não se aplica à API Web de comunicações unificadas (UCWA), conforme fornecido nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

Ao instalar o serviço de mobilidade (MCX) nos serviços de informações da Internet (IIS) 7,5, o instalador do serviço de mobilidade configura algumas configurações de desempenho no servidor front-end. Recomendamos o uso do IIS 7.5 para mobilidade. As configurações afetam o número máximo de solicitações de usuário simultâneas e o número máximo de segmentos permitidos para o Serviço de Mobilidade.

Aqui estão as configurações de desempenho:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Configurações para MCX no IIS 7,5

1.  **maxConcurrentThreadsPerCPU** está definido como zero (0).

2.  **maxConcurrentRequestsPerCPU** está definido como zero (0).

3.  O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).

4.  O limite de fila HTTP.sys está definido como 1.000 (por padrão).

</div>

</div>

<span> </span>

</div>

</div>

</div>

