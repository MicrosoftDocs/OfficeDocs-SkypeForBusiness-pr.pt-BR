---
title: 'Lync Server 2013: Bypass de mídia e Servidor de Mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="be76f-102">Bypass de mídia e Servidor de Mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be76f-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be76f-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="be76f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="be76f-104">O bypass de mídia é um recurso do Lync Server que permite que um administrador configure o roteamento de chamadas para fluir diretamente entre o ponto de extremidade do usuário e o gateway PSTN (rede telefônica pública comutada) sem atravessar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="be76f-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="be76f-105">O bypass de mídia melhora a qualidade da chamada reduzindo a latência, a tradução desnecessária, a possibilidade de perda de pacotes e a quantidade de pontos de falha em potencial.</span><span class="sxs-lookup"><span data-stu-id="be76f-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="be76f-106">Quando um site remoto sem um servidor de mediação está conectado a um site central por um ou mais links de WAN com largura de banda restrita, o bypass de mídia reduz a necessidade de largura de banda habilitando a mídia de um cliente em um site remoto para fluir diretamente para seu gateway local sem Primeiro, é necessário fluir pelo link de WAN para um servidor de mediação no site central e para trás. Essa redução no processamento de mídia também complementa a capacidade do servidor de mediação de controlar vários gateways.</span><span class="sxs-lookup"><span data-stu-id="be76f-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="be76f-p102">O bypass de mídia e o CAC (controle de admissão de chamadas) são mutuamente exclusivos. Se o bypass de mídia for empregado para uma chamada, o CAC não será executado para essa chamada. Presume-se que não haja links com largura de banda restrita envolvidos na chamada.</span><span class="sxs-lookup"><span data-stu-id="be76f-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="be76f-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="be76f-110">See Also</span></span>


[<span data-ttu-id="be76f-111">Controle de admissão de chamada e Servidor de Mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be76f-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="be76f-112">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be76f-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

