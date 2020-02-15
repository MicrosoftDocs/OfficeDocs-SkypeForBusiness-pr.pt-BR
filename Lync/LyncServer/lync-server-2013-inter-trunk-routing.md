---
title: 'Lync Server 2013: roteamento entre troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 587b908cbbff1b69f04fa285fd60a18c28992efb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="af531-102">Roteamento entre troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af531-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af531-103">_**Última modificação do tópico:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="af531-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="af531-104">O Lync Server 2013 fornece gerenciamento de sessão básica através do suporte de roteamento entre troncos.</span><span class="sxs-lookup"><span data-stu-id="af531-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="af531-105">Esse novo recurso permite que o Lync Server forneça funcionalidades de controle de chamada para sistemas de telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="af531-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="af531-106">O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX.</span><span class="sxs-lookup"><span data-stu-id="af531-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="af531-107">Da mesma forma, o Lync Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser colocadas e recebidas entre os telefones PBX dos diferentes sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="af531-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="af531-108">A figura a seguir ilustra o Lync Server 2013 fornecendo interconectividade entre um gateway PSTN e um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="af531-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="af531-109">![O diagrama de gateway PSTN/IP-PBX de conexão do Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "O diagrama de gateway PSTN/IP-PBX de conexão do Lync Server")</span><span class="sxs-lookup"><span data-stu-id="af531-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="af531-110">A próxima figura ilustra o Lync Server 2013 conectando dois sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="af531-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="af531-111">![Diagrama de sistemas IP-PAX de interconexão do Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de sistemas IP-PAX de interconexão do Lync Server")</span><span class="sxs-lookup"><span data-stu-id="af531-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

