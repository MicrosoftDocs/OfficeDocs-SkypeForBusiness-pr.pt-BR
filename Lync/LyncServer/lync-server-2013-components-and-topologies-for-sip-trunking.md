---
title: 'Lync Server 2013: componentes e topologias para tronco SIP'
description: 'Lync Server 2013: componentes e topologias para tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d9c826539084a539d3efe7f143c335ec6d8f62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549517"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="f4498-103">Componentes e topologias para tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4498-103">Components and topologies for SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4498-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f4498-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f4498-105">A figura a seguir ilustra a topologia de tronco SIP no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4498-105">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="f4498-106">**Topologia de tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="f4498-106">**SIP trunking topology**</span></span>

<span data-ttu-id="f4498-107">![Topologia de tronco SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia de tronco SIP")</span><span class="sxs-lookup"><span data-stu-id="f4498-107">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="f4498-108">Conforme mostrado no diagrama, uma rede virtual privada (VPN) de IP é usada para conectividade entre a rede corporativa e o provedor de serviços PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="f4498-108">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="f4498-109">A finalidade dessa rede privada é fornecer conectividade IP, aumentar a segurança e (opcionalmente) obter garantias de qualidade de serviço (QoS).</span><span class="sxs-lookup"><span data-stu-id="f4498-109">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="f4498-110">Devido à natureza de uma VPN, não é necessário usar o protocolo TLS (Transport Layer Security) para o tráfego de sinalização SIP ou SRTP (Secure real-time Transport Protocol) para o tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="f4498-110">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="f4498-111">As conexões entre a empresa e o provedor de serviços consistem em conexões TCP simples para SIP e RTP (protocolo de transporte em tempo real) simples (via UDP) para mídia encapsulada por meio de uma VPN IP.</span><span class="sxs-lookup"><span data-stu-id="f4498-111">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="f4498-112">Certifique-se de que todos os firewalls entre os roteadores VPN tenham portas abertas para permitir que os roteadores VPN se comuniquem e que os endereços IP nas bordas externas dos roteadores VPN sejam roteáveis publicamente.</span><span class="sxs-lookup"><span data-stu-id="f4498-112">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f4498-113">Entre em contato com seu provedor de serviços para determinar se ele oferece suporte para alta disponibilidade, incluindo failover.</span><span class="sxs-lookup"><span data-stu-id="f4498-113">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="f4498-114">Em caso afirmativo, será necessário determinar os procedimentos para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="f4498-114">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="f4498-115">Por exemplo, você precisa configurar apenas um endereço IP e um tronco SIP em cada servidor de mediação ou precisa configurar vários troncos SIP em cada servidor de mediação?</span><span class="sxs-lookup"><span data-stu-id="f4498-115">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="f4498-116">Se você tiver vários sites centrais, verifique também se o provedor de serviços tem a capacidade de habilitar conexões de e para outro site central.</span><span class="sxs-lookup"><span data-stu-id="f4498-116">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f4498-117">Para troncos SIP, é altamente recomendável implantar servidores de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="f4498-117">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="f4498-118">Para obter detalhes, consulte <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and define Peers in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f4498-118">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="f4498-119">Protegendo o servidor de mediação para tronco SIP</span><span class="sxs-lookup"><span data-stu-id="f4498-119">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="f4498-120">Para fins de segurança, você deve configurar uma VLAN (LAN virtual) para cada conexão entre os dois roteadores VPN.</span><span class="sxs-lookup"><span data-stu-id="f4498-120">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="f4498-121">O processo real para configurar uma VLAN varia de um fabricante de roteador para outro.</span><span class="sxs-lookup"><span data-stu-id="f4498-121">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="f4498-122">Para obter detalhes, entre em contato com o fornecedor do roteador.</span><span class="sxs-lookup"><span data-stu-id="f4498-122">For details, contact your router vendor.</span></span>

<span data-ttu-id="f4498-123">Recomendamos que você siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="f4498-123">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="f4498-124">Configure uma LAN virtual (VLAN) entre o servidor de mediação e o roteador VPN na rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada).</span><span class="sxs-lookup"><span data-stu-id="f4498-124">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="f4498-125">Não permita que pacotes de difusão ou multicast sejam transferidos do roteador para a VLAN.</span><span class="sxs-lookup"><span data-stu-id="f4498-125">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="f4498-126">Bloquear qualquer regra de roteamento que roteia o tráfego do roteador para qualquer lugar, exceto o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f4498-126">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="f4498-127">Se você usar um servidor VPN, recomendamos seguir estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="f4498-127">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="f4498-128">Configure uma VLAN entre o servidor VPN e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f4498-128">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="f4498-129">Não permita que pacotes de difusão ou multicast sejam transmitidos do servidor VPN para a VLAN.</span><span class="sxs-lookup"><span data-stu-id="f4498-129">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="f4498-130">Bloquear qualquer regra de roteamento que roteia o tráfego do servidor VPN para qualquer lugar, exceto o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f4498-130">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="f4498-131">Criptografe os dados na VPN usando o GRE (encapsulamento de roteamento genérico).</span><span class="sxs-lookup"><span data-stu-id="f4498-131">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

