---
title: 'Lync Server 2013: Modos de bypass de mídia'
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
ms.openlocfilehash: 4f92d45099f39ec96724f8d0f6025f58e2dbccb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41761947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>Modos de bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

Configure o bypass de mídia globalmente e para cada tronco PSTN individual. Ao habilitar o bypass de mídia globalmente, você tem duas opções: **Sempre ignorar** e **Use Site and Region Information** (Usar informações do site e da região).

Como o nome sugere, **Sempre ignorar** significa que o bypass será tentado para todas as chamadas de PSTN. **Sempre ignorar** é usado para as implantações em que não há necessidade de ativar o controle de admissão da chamada, e nem de especificar informações detalhadas da configuração de quando tentar o bypass de mídia. Além disso, **Sempre ignorar** é usado quando existe uma conectividade total entre os clientes e os gateways de PSTN. Nesta configuração, todas as sub-redes são mapeadas apenas para um ID de bypass, que é calculado pelo sistema.

Com **Use Site and Region Information** (Usar informações do site e da região), a ID de bypass é associada à configuração do site e de região usada para tomar a decisão do bypass. Essa configuração fornece a flexibilidade de configurar o bypass para as topologias mais comuns, porque permite um controle refinado de quando o bypass acontece, além de oferecer suporte às interações com o serviço de controle de admissão de chamadas (CAC). O sistema tentar facilitar sua tarefa, atribuindo automaticamente IDs de bypass conforme indicado a seguir.

  - O sistema atribui automaticamente uma única ID de bypass exclusiva para cada região.

  - Qualquer site conectado a uma região via link WAN, sem restrições de largura de banda, herda a mesma ID de bypass que a região.

  - Um site associado à região via link WAN com largura de banda restrita é atribuído a uma ID de bypass diferente do da região.

  - As sub-redes associadas a cada site herdam a ID de bypass do site.

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

