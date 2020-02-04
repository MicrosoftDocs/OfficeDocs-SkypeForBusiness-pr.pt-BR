---
title: 'Lync Server 2013: associar sub-redes a sites de rede para o CAC'
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
ms.openlocfilehash: bf447b2e34ff4f274ebcab9d36e40b65bedab7dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="45ae8-102">Associar sub-redes a sites de rede de CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ae8-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ae8-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="45ae8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="45ae8-104">Todas as sub-redes na rede devem estar associadas a um site de rede específico.</span><span class="sxs-lookup"><span data-stu-id="45ae8-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="45ae8-105">Isso ocorre porque as informações de sub-rede são usadas para determinar o site de rede no qual se encontra um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="45ae8-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="45ae8-106">Quando os locais de ambas as partes de uma sessão são conhecidos, o controle de admissão de chamadas (CAC) pode determinar se há largura de banda suficiente para estabelecer uma chamada.</span><span class="sxs-lookup"><span data-stu-id="45ae8-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="45ae8-107">O controle de admissão de chamadas não tem nenhum requisito especial para associar sub-redes a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="45ae8-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="45ae8-108">Para criar uma associação entre as sub-redes e os sites de rede em sua topologia, siga os procedimentos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="45ae8-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="45ae8-109">Para exibir os sites de rede (e suas respectivas sub-redes) na topologia de rede de exemplo para o controle de admissão de chamadas, consulte [exemplo: reunir seus requisitos de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="45ae8-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

