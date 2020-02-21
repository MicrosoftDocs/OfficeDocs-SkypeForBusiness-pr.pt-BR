---
title: 'Lync Server 2013: considerações técnicas para roteamento baseado em local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89180087909b71bc9f53f24ee02bbc077d459a17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Considerações técnicas para roteamento baseado em local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

Ao planejar o roteamento baseado em local, considere o impacto nos cenários a seguir.

<div>

## <a name="disaster-recovery"></a>Recuperação de desastre

Durante um failover do pool primário para um pool de backup, bem como durante a restauração de operações normais para o pool primário, o roteamento baseado em local permanecerá em vigor em todos os momentos durante um desastre e procedimento de recuperação.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Aplicativo de Filial Persistente

Configurar o roteamento baseado em local impacta o planejamento de onde você implanta os gateways associados aos seus aparelhos de filial persistentes. O gateway associado ao seu SBA deve estar localizado no mesmo local de rede que seu aparelho de filial persistente; caso contrário, os usuários hospedados no seu aparelho de filial persistente não terão permissão para fazer chamadas de saída se o roteamento baseado em local estiver configurado. Quando a conexão WAN entre seu aparelho de filial persistente e o site central estiver inativa, as restrições de roteamento baseadas em local permanecerão impostas.

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de roteamento baseado em local no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

