---
title: 'Lync Server 2013: modos de bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56e3c70e8bfc1a475436df97e4f2e3a5b4f32689
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>Modos de bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Configure o desvio de mídia globalmente e para cada tronco PSTN individual. Ao habilitar o desvio de mídia globalmente, você tem duas opções: **Sempre Ignorar** e **Usar Informações de Local e Região**.

Como o nome sugere, **Sempre Desviar** significa que o desvio será tentado para todas as chamadas de PSTN. **Sempre Desviar** é usado para as implantações em que não há necessidade de ativar o controle de admissão da chamada, e nem de especificar informações detalhadas da configuração de quando tentar o desvio de mídia. Além disso, **Sempre Desviar** é usado quando existe uma conectividade total entre os clientes e os gateways de PSTN. Nesta configuração, todas as sub-redes são mapeadas apenas para um ID de desvio, que é calculado pelo sistema.

Quando **Usar Informações do Local e Região**, o ID do desvio é associado à configuração do local e de região usada para tomar a decisão do desvio. Essa configuração fornece a flexibilidade de configurar o desvio para as topologias mais comuns, porque permite um controle refinado de quando o desvio acontece, além de suportar as interações com o controle de admissão de chamadas (CAC). O sistema tentar aliviar sua tarefa, atribuindo automaticamente os IDs de desvio conforme segue.

  - O sistema atribui automaticamente um único ID de desvio exclusivo para cada região.

  - Qualquer local conectado a uma região via link WAN, sem restrições de largura de banda, herda o mesmo ID de desvio que a região.

  - Um local associado à região via link WAN com largura de banda restrita é atribuído a um ID de desvio diferente do da região.

  - As sub-redes associadas a cada site herdam o ID de desvio do site.

<div>

## <a name="see-also"></a>Confira também


[Visão geral do bypass de mídia no Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Bypass de mídia e controle de admissão de chamadas no Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para bypass de mídia no Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

