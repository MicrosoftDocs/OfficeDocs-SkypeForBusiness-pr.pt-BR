---
title: Sites do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3342fb05a0ad843be9e4b6b065507a368e1c4556
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="b8bf6-102">Sites do Lync Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8bf6-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8bf6-103">_**Última modificação do tópico:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="b8bf6-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="b8bf6-104">No Lync Server, você define *sites* em sua rede que contenham componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="b8bf6-105">Um site é um conjunto de computadores bem conectados por uma rede de alta velocidade e baixa latência, como uma rede local (LAN) única ou duas redes conectadas por uma rede óptica de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="b8bf6-106">Observe que os sites do Lync Server são um conceito separado dos sites dos serviços de domínio do Active Directory e dos sites do Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="b8bf6-107">Seus sites do Lync Server não precisam corresponder aos sites do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="b8bf6-108">Tipos de Site</span><span class="sxs-lookup"><span data-stu-id="b8bf6-108">Site Types</span></span>

<span data-ttu-id="b8bf6-109">Cada site é um *site central*, que contém pelo menos um pool de front-ends ou um servidor Standard Edition, ou um *site de filial*.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="b8bf6-110">Cada site de filial é associado a um site central, e os usuários no site de filial obtêm a maior parte da funcionalidade do Lync Server dos servidores no site central associado.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="b8bf6-111">Cada site de filial contem ao menos um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="b8bf6-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="b8bf6-112">Um *aparelho de filial persistente (SBA)*, que é um servidor de lâmina padrão da indústria com um registrador do Lync Server e um servidor de mediação executando no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="b8bf6-113">O aparelho de filial persistente também contém um gateway PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="b8bf6-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="b8bf6-114">O aparelho de filial persistente foi projetado para sites de filiais com entre 25 e 1000 usuários.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="b8bf6-115">Um *servidor de ramificação persistente (SBS)*, que é um servidor que executa o Windows Server e que atende aos requisitos de hardware especificados, e que tem o software de servidor de mediação e registrador do Lync Server instalado nele.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="b8bf6-116">Ele deve se conectar ao gateway PSTN ou tronco SIP para um provedor de serviço telefônico.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="b8bf6-117">O Servidor de Filial Sustentável foi projetado para sites de filial com 1000 a 5000 usuários.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="b8bf6-118">Um gateway PSTN e opcionalmente um *Servidor de Mediação*.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="b8bf6-119">Para obter detalhes sobre esta e outras funções de servidor, consulte [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b8bf6-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="b8bf6-120">Uma filial com um link WAN (rede de longa distância) resistente à um site central pode usar a terceira opção, um gateway PSTN e, opcionalmente, um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="b8bf6-121">Os sites de filiais com links menos resistentes devem usar um aparelho de filial persistente ou servidor de filial persistente, que oferecem resiliência em horários de falhas de rede de longa distância.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="b8bf6-122">Por exemplo, em um site com um aparelho de filial persistente ou servidor de filial persistente implantado, os usuários ainda poderão fazer e receber chamadas do Enterprise Voice se a WAN conectando o site de filial ao site central estiver desativada.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="b8bf6-123">Para obter detalhes sobre o aparelho de filial persistente, servidor de filial persistente e resiliência, consulte [Planning for Enterprise Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="b8bf6-124">Topologias de Site</span><span class="sxs-lookup"><span data-stu-id="b8bf6-124">Site Topologies</span></span>

<span data-ttu-id="b8bf6-125">Sua implantação deve incluir ao menos um site central e pode incluir de nenhum a muitos sites de filial.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="b8bf6-126">Cada site de filial é afiliado a um site central.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="b8bf6-127">O site central fornece os serviços do Lync Server para o site de filial que não estão hospedados localmente no site de filial, como presença e conferência.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="b8bf6-128">Se você possuir vários sites, pode pareá-los juntos nos pools de Front End em diferentes sites para ativar as capacidades de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="b8bf6-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="b8bf6-129">Para obter detalhes, consulte [High Availability and Disaster Recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="b8bf6-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8bf6-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="b8bf6-130">See Also</span></span>


[<span data-ttu-id="b8bf6-131">Funções de servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8bf6-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="b8bf6-132">Suporte de alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8bf6-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="b8bf6-133">Planejamento para resiliência do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8bf6-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

