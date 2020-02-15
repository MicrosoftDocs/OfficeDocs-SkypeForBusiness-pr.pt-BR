---
title: 'Lync Server 2013: modos de bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af12e34f66d21e447963d857b26976fc130202fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="3ca51-102">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca51-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ca51-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3ca51-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3ca51-p101">Configure o desvio de mídia globalmente e para cada tronco PSTN individual. Ao habilitar o desvio de mídia globalmente, você tem duas opções: **Sempre Ignorar** e **Usar Informações de Local e Região**.</span><span class="sxs-lookup"><span data-stu-id="3ca51-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="3ca51-p102">Como o nome sugere, **Sempre Desviar** significa que o desvio será tentado para todas as chamadas de PSTN. **Sempre Desviar** é usado para as implantações em que não há necessidade de ativar o controle de admissão da chamada, e nem de especificar informações detalhadas da configuração de quando tentar o desvio de mídia. Além disso, **Sempre Desviar** é usado quando existe uma conectividade total entre os clientes e os gateways de PSTN. Nesta configuração, todas as sub-redes são mapeadas apenas para um ID de desvio, que é calculado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="3ca51-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="3ca51-p103">Quando **Usar Informações do Local e Região**, o ID do desvio é associado à configuração do local e de região usada para tomar a decisão do desvio. Essa configuração fornece a flexibilidade de configurar o desvio para as topologias mais comuns, porque permite um controle refinado de quando o desvio acontece, além de suportar as interações com o controle de admissão de chamadas (CAC). O sistema tentar aliviar sua tarefa, atribuindo automaticamente os IDs de desvio conforme segue.</span><span class="sxs-lookup"><span data-stu-id="3ca51-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="3ca51-113">O sistema atribui automaticamente um único ID de desvio exclusivo para cada região.</span><span class="sxs-lookup"><span data-stu-id="3ca51-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="3ca51-114">Qualquer local conectado a uma região via link WAN, sem restrições de largura de banda, herda o mesmo ID de desvio que a região.</span><span class="sxs-lookup"><span data-stu-id="3ca51-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="3ca51-115">Um local associado à região via link WAN com largura de banda restrita é atribuído a um ID de desvio diferente do da região.</span><span class="sxs-lookup"><span data-stu-id="3ca51-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="3ca51-116">As sub-redes associadas a cada site herdam o ID de desvio do site.</span><span class="sxs-lookup"><span data-stu-id="3ca51-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3ca51-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="3ca51-117">See Also</span></span>


[<span data-ttu-id="3ca51-118">Visão geral do bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca51-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="3ca51-119">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca51-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="3ca51-120">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca51-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

