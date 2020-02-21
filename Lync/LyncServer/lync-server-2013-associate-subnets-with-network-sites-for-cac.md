---
title: 'Lync Server 2013: associar sub-redes a sites de rede para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfe2b41293d58223817a06eef82f5c03d0909a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="a052d-102">Associar sub-redes a sites de rede para CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a052d-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a052d-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a052d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a052d-p101">Todas as sub-redes em sua rede devem ser associadas a um site de rede específico. A razão para isso é que as informações de sub-rede são usadas para determinar o site de rede em que um ponto de extremidade está localizado. Quando os locais de ambas as partes de uma sessão são conhecidos, o controle de admissão de chamadas (CAC) pode determinar se há largura de banda suficiente para estabelecer uma chamada.</span><span class="sxs-lookup"><span data-stu-id="a052d-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="a052d-107">O controle de admissão de chamadas não possui requisitos especiais para associar sub-redes a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="a052d-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="a052d-108">Para criar uma associação entre as sub-redes e os sites de rede em sua topologia, siga os procedimentos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="a052d-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="a052d-109">Para exibir os sites de rede (e suas respectivas sub-redes) no exemplo de topologia de rede para controle de admissão de chamadas, confira o [exemplo: coletando seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a052d-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

