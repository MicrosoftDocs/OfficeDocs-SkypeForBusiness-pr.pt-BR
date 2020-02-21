---
title: 'Lync Server 2013: controle de admissão de chamada e servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf738bbd0bd66834082983f78de56bb23bfc33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Controle de admissão de chamadas e servidor de mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O CAC (controle de admissão de chamadas), introduzido pela primeira vez no Lync Server 2010, gerencia o estabelecimento de sessão em tempo real, com base na largura de banda disponível, para ajudar a evitar má qualidade da experiência (QoE) para usuários em redes congestionadas. Para dar suporte a esse recurso, o servidor de mediação, que fornece sinalização e conversão de mídia entre a infraestrutura Enterprise Voice e um gateway ou provedor de tronco SIP, é responsável pelo gerenciamento de largura de banda para suas duas interações no Lync Lado do servidor e no lado do gateway. No controle de admissão de chamadas, a entidade de terminação de uma chamada lida com a reserva da largura de banda. Os pares de gateway (gateway PSTN, IP-PBX, SBC) que o servidor de mediação interage no lado do gateway não oferecem suporte ao Lync Server 2013 Call Admission Control. Portanto, o servidor de mediação precisa lidar com as interações de largura de banda em nome de seu ponto de gateway. Sempre que possível, o servidor de mediação reservará a largura de banda antecipadamente. Se isso não for possível (por exemplo, a localidade do ponto de extremidade da mídia final no lado do gateway for desconhecido para uma chamada feita para o par de gateway), a largura de banda será reservada quando a chamada for feita. Esse comportamento pode resultar em uma inscrição em excesso da largura de banda, mas é a única maneira de impedir anéis falsos.

O bypass de mídia e o modo de reserva da largura de banda são mutuamente exclusivos. Se um bypass de mídia é empregado para uma chamada, o controle de admissão de chamada não é executado para essa chamada. O pressuposto é que não há links com largura de banda restrita envolvidos na chamada. Se o controle de admissão de chamadas for usado para uma chamada específica que envolve o servidor de mediação, essa chamada não poderá empregar o bypass de mídia.

Para obter detalhes sobre o bypass de mídia ou controle de admissão de chamada, consulte [Planning for Media bypass in Lync server 2013](lync-server-2013-planning-for-media-bypass.md) ou [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) na documentação de planejamento.

</div>

<span> </span>

</div>

</div>

</div>

