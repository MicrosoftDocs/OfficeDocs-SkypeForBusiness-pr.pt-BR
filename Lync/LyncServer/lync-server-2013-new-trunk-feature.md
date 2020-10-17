---
title: 'Lync Server 2013: novo recurso de tronco'
description: 'Lync Server 2013: novo recurso de tronco.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f923ceada899608cc350bd1343345c12d0996b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541937"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="f972d-103">Novo recurso de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f972d-103">New trunk feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f972d-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f972d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f972d-105">No Microsoft Lync Server 2013, vários troncos entre um servidor de mediação e um gateway podem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="f972d-105">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="f972d-106">O Microsoft Lync Server 2010 é permitido apenas para um único tronco entre um servidor de mediação e um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f972d-106">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="f972d-107">Esse recurso oferece a flexibilidade para definir troncos adicionais.</span><span class="sxs-lookup"><span data-stu-id="f972d-107">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="f972d-108">Um tronco é uma associação lógica entre um FQDN do servidor de mediação e uma porta de escuta e um FQDN de gateway PSTN e uma porta de escuta.</span><span class="sxs-lookup"><span data-stu-id="f972d-108">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="f972d-109">Esse novo recurso permite uma definição de tronco fácil para resiliência (onde vários servidores de mediação podem ser usados para rotear chamadas para o mesmo gateway PSTN) para a interoperabilidade de PBX, onde vários troncos com políticas associadas diferentes podem ser usados entre o IP-PBX e um servidor de mediação e as configurações de tronco SIP, onde os servidores de mediação em diferentes sites têm troncos SIP para a portadora referenciada pelo mesmo FQDN da operadora.</span><span class="sxs-lookup"><span data-stu-id="f972d-109">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f972d-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="f972d-110">See Also</span></span>


[<span data-ttu-id="f972d-111">Novos recursos do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f972d-111">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

