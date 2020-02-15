---
title: 'Lync Server 2013: conexões SIP diretas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edd6c7cbcaa1789d9f37cd77123b4afd8c2416de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="556a1-102">Conexões SIP diretas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a1-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="556a1-103">_**Última modificação do tópico:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="556a1-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="556a1-104">Você pode usar *conexões SIP diretas* para conectar o Lync Server a um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="556a1-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="556a1-105">Um IP-PBX (para obter detalhes, consulte [Direct SIP Deployment Options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="556a1-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="556a1-106">Um gateway PSTN (para obter detalhes, consulte [Opções de implantação de gateway PSTN no Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="556a1-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="556a1-107">Para implantar uma conexão SIP direta, você segue, basicamente, as mesmas etapas de implantação de um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="556a1-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="556a1-108">Em ambos os casos, você implementa a conexão usando a interface externa de um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="556a1-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="556a1-109">A única diferença é que você conecta os troncos SIP a uma entidade externa, como um gateway ITSP, e conecta as conexões SIP diretas a uma entidade interna dentro da sua rede local, como um IP-PBX ou um gateway de uma Rede Telefônica Pública Comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="556a1-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="556a1-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="556a1-110">In This Section</span></span>

  - [<span data-ttu-id="556a1-111">Opções de implantação de SIP direto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a1-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="556a1-112">Opções de implantação de gateway PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="556a1-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

