---
title: 'Lync Server 2013: colocação de servidor suportado para componentes de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71c8e30cfd4257982781e446a61c18518b570e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523998"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="b0147-102">Colocação de servidor suportado para componentes de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0147-102">Supported server collocation for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0147-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b0147-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b0147-104">O serviço de borda de acesso, o serviço de borda de webconferência, o serviço de borda A/V e o serviço de proxy do XMPP são colocados nos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="b0147-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="b0147-105">Os servidores fornecem funções necessárias para o acesso de usuário externo e devem ser implantados como servidores dedicados:</span><span class="sxs-lookup"><span data-stu-id="b0147-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="b0147-106">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b0147-106">Edge Server</span></span>

  - <span data-ttu-id="b0147-107">Diretor (opcional)</span><span class="sxs-lookup"><span data-stu-id="b0147-107">Director (Optional)</span></span>

  - <span data-ttu-id="b0147-108">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="b0147-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b0147-109">O proxy reverso não precisa ser dedicado para servir somente o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0147-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="b0147-110">Por exemplo, você pode fornecer serviços para publicar os serviços Web do Lync Server e, simultaneamente, fornecer um site da Web publicado para outro site que não tenha nenhum rumo no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0147-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="b0147-111">Se você já tiver um servidor de proxy reverso na rede de perímetro para dar suporte a outros serviços, poderá usá-lo para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0147-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

