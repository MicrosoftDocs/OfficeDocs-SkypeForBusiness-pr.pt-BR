---
title: 'Lync Server 2013: associar sub-redes a sites de rede para bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5565be047443ebb0bf84358a592dc0b1f9314c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a4177-102">Associar sub-redes a sites de rede para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4177-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4177-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a4177-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4177-104">Este tópico assume que você tenha definido as configurações globais de desvio de mídia, a região da rede e os locais de rede para desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="a4177-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="a4177-p101">Cada sub-rede em sua rede deve ser associada a um site de rede específico. Isso ocorre porque as informações da sub-rede são usadas para determinar o site de rede no qual um ponto de extremidade está localizado. Quando os locais de ambas as partes em uma sessão são conhecidos, os desvio de mídia pode determinar para onde a mídia é enviada para processamento.</span><span class="sxs-lookup"><span data-stu-id="a4177-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="a4177-108">O desvio de mídia não tem requisitos especiais para associar sub-redes a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="a4177-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="a4177-109">Para criar uma associação entre as sub-redes e os sites de rede em sua topologia, siga os procedimentos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="a4177-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="a4177-110">Próximas etapas: criar perfis de políticas de largura de banda</span><span class="sxs-lookup"><span data-stu-id="a4177-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="a4177-p103">Depois de associar sub-redes a sites da rede para o desvio de mídia, você deverá criar um ou mais perfis de política de largura de banda que dividirão as sub-redes entre aquelas com boa conectividade e aquelas sem, para fins de desvio de mídia. Todas as sub-redes em uma região com sites de rede que não têm restrições de largura de banda possuem boa conectividade e, portanto, essas sub-redes podem usar o desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="a4177-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="a4177-113">Para obter os procedimentos para configurar perfis de política de largura de banda, consulte [Create Bandwidth Policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a4177-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

