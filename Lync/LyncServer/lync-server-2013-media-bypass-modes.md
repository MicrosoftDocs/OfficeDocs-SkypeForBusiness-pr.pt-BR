---
title: 'Lync Server 2013: Modos de bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a08ec3ae6d985c18e20964a857a74ad40bc7668d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="1ca7d-102">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca7d-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ca7d-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="1ca7d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="1ca7d-p101">Configure o bypass de mídia globalmente e para cada tronco PSTN individual. Ao habilitar o bypass de mídia globalmente, você tem duas opções: **Sempre ignorar** e **Use Site and Region Information** (Usar informações do site e da região).</span><span class="sxs-lookup"><span data-stu-id="1ca7d-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="1ca7d-p102">Como o nome sugere, **Sempre ignorar** significa que o bypass será tentado para todas as chamadas de PSTN. **Sempre ignorar** é usado para as implantações em que não há necessidade de ativar o controle de admissão da chamada, e nem de especificar informações detalhadas da configuração de quando tentar o bypass de mídia. Além disso, **Sempre ignorar** é usado quando existe uma conectividade total entre os clientes e os gateways de PSTN. Nesta configuração, todas as sub-redes são mapeadas apenas para um ID de bypass, que é calculado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="1ca7d-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="1ca7d-p103">Com **Use Site and Region Information** (Usar informações do site e da região), a ID de bypass é associada à configuração do site e de região usada para tomar a decisão do bypass. Essa configuração fornece a flexibilidade de configurar o bypass para as topologias mais comuns, porque permite um controle refinado de quando o bypass acontece, além de oferecer suporte às interações com o serviço de controle de admissão de chamadas (CAC). O sistema tentar facilitar sua tarefa, atribuindo automaticamente IDs de bypass conforme indicado a seguir.</span><span class="sxs-lookup"><span data-stu-id="1ca7d-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="1ca7d-113">O sistema atribui automaticamente uma única ID de bypass exclusiva para cada região.</span><span class="sxs-lookup"><span data-stu-id="1ca7d-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="1ca7d-114">Qualquer site conectado a uma região via link WAN, sem restrições de largura de banda, herda a mesma ID de bypass que a região.</span><span class="sxs-lookup"><span data-stu-id="1ca7d-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="1ca7d-115">Um site associado à região via link WAN com largura de banda restrita é atribuído a uma ID de bypass diferente do da região.</span><span class="sxs-lookup"><span data-stu-id="1ca7d-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="1ca7d-116">As sub-redes associadas a cada site herdam a ID de bypass do site.</span><span class="sxs-lookup"><span data-stu-id="1ca7d-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1ca7d-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="1ca7d-117">See Also</span></span>


[<span data-ttu-id="1ca7d-118">Visão geral do bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca7d-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="1ca7d-119">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca7d-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="1ca7d-120">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca7d-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

