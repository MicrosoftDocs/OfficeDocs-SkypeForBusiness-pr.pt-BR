---
title: 'Lync Server 2013: Configurando o serviço de mobilidade para alto desempenho'
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
ms.openlocfilehash: 29eaea1e45c5d3b745debbc2f97370a76e6d16db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Configurando o serviço de mobilidade para alto desempenho no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Este tópico se aplica apenas ao serviço de mobilidade do Lync Server 2013 (MCX) e não se aplica à API da Web de comunicação unificada (UCWA), conforme entregue nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

Quando você instala o serviço de mobilidade (MCX) em serviços de informações da Internet (IIS) 7,5, o instalador do serviço de mobilidade configura algumas configurações de desempenho no servidor front-end. Recomendamos usar IIS 7.5 para mobilidade. As configurações afetam o número máximo de solicitações concomitantes de usuários e o número máximo de threads permitidos para o Mobility Service.

Aqui estão as configurações de desempenho:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Configurações para Mcx no IIS 7.5

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

