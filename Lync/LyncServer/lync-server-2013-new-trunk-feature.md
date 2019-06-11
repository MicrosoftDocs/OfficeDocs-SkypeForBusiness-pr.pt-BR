---
title: 'Lync Server 2013: Novo recurso de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18296a9d1da060c9faaf8d4c765c38403a9cb224
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="ac5d9-102">Novo recurso de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac5d9-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac5d9-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ac5d9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ac5d9-104">No Microsoft Lync Server 2013, vários troncos entre um servidor de mediação e um gateway podem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="ac5d9-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="ac5d9-105">O Microsoft Lync Server 2010 é permitido apenas para um único tronco entre um servidor de mediação e um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ac5d9-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="ac5d9-106">Esse recurso fornece a flexibilidade para definir troncos adicionais.</span><span class="sxs-lookup"><span data-stu-id="ac5d9-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="ac5d9-107">Um tronco é uma associação lógica entre um FQDN do servidor de mediação e uma porta de escuta e uma porta de escuta e FQDN do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ac5d9-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="ac5d9-108">Essa nova funcionalidade permite uma definição de tronco fácil para resiliência (em que vários servidores de mediação podem ser usados para direcionar chamadas para o mesmo gateway PSTN), para interoperabilidade de PBX, em que vários troncos com políticas associadas diferentes podem ser usados entre e IP-PBX e um servidor de mediação e para configurações de tronco SIP em que os servidores de mediação em diferentes locais têm troncos SIP para a transportadora referenciadas pelo mesmo FQDN da operadora.</span><span class="sxs-lookup"><span data-stu-id="ac5d9-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ac5d9-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="ac5d9-109">See Also</span></span>


[<span data-ttu-id="ac5d9-110">Novos recursos do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac5d9-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

