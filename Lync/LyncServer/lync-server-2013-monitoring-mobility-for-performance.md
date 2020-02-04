---
title: 'Lync Server 2013: monitorando a mobilidade para desempenho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Monitorando a mobilidade para o desempenho no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-14_

O serviço de mobilidade do Lync Server (MCX) e a API da Web de comunicação unificada (UCWA) aumentam a carga em servidores front-end e em pools front-end. Dispositivos móveis que mantêm uma conexão com o servidor, mesmo quando o aplicativo móvel é minimizado, como dispositivos Android e Nokia que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple que executam o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que Termine a conexão com o servidor quando o aplicativo móvel estiver minimizado. Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.

Vários limites influenciam o desempenho da mobilidade:

  - Memória disponível

  - Limite da fila de solicitações

  - Conexões concorrentes

  - Tamanho da fila do IIS

Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze entradas simultâneas, autenticações, renovações de sessão e resterminações. Esses máximos não precisam ser modificados para a maioria das implantações.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Monitorar os limites de capacidade de memória do servidor no Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Monitorar o serviço de mobilidade e o uso do UCWA no Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configurando o serviço de mobilidade para alto desempenho no Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Monitorar arquivos de log de rastreamento de solicitação do IIS no Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Contadores de desempenho de mobilidade no Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

