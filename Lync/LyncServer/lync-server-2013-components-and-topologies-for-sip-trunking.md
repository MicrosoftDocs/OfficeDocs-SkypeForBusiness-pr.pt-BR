---
title: 'Lync Server 2013: Componentes e topologias para tronco SIP'
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
ms.openlocfilehash: d30c589ff02717ad49ce89d0d4e3324f6fe993e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="2879c-102">Componentes e topologias para tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2879c-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2879c-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2879c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2879c-104">A figura a seguir ilustra a topologia de entroncamento SIP no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2879c-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="2879c-105">**Topologia de troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="2879c-105">**SIP trunking topology**</span></span>

<span data-ttu-id="2879c-106">![Topologia de entroncamento SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia de entroncamento SIP")</span><span class="sxs-lookup"><span data-stu-id="2879c-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="2879c-p101">Conforme mostra o diagrama, uma VPN (rede virtual privada) IP é usada para a conectividade entre a rede corporativa e o provedor de serviços da rede de telefonia pública comutada (PSTN). O objetivo desta rede privada é fornecer conectividade IP, aprimorar a segurança e (opcionalmente) obter garantias de qualidade de serviços (QoS). Devido à natureza de uma VPN, não é necessário usar protocolo TLS para o tráfego de sinalização SIP ou SRTP para tráfego de mídia.  As conexões entre a empresa e o provedor de serviços consistem, portanto, em conexões TCP básicas para SIP e RTP básico (via protocolo UDP) em mídia encapsulada através de uma VPN IP. Certifique-se de que todos os firewalls entre os roteadores VPN possuem portas abertas para permitir a comunicação e que os endereços IP nas bordas externas dos roteadores VPN sejam roteáveis publicamente.</span><span class="sxs-lookup"><span data-stu-id="2879c-p101">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2879c-112">Contate seu provedor de serviços para determinar se ele oferece suporte para alta disponibilidade, incluindo failover.</span><span class="sxs-lookup"><span data-stu-id="2879c-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="2879c-113">Em caso positivo, você precisará determinar os procedimentos para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="2879c-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="2879c-114">Por exemplo, você precisa configurar apenas um endereço IP e um tronco SIP em cada servidor de mediação ou precisa configurar vários troncos SIP em cada servidor de mediação?</span><span class="sxs-lookup"><span data-stu-id="2879c-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="2879c-115">Se você tiver vários sites centrais, verifique também se o provedor de serviço tem a capacidade de habilitar conexões para e de outro site central.</span><span class="sxs-lookup"><span data-stu-id="2879c-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2879c-116">Para o entroncamento SIP, é altamente recomendável implantar servidores de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="2879c-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="2879c-117">Para obter detalhes, consulte <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">implantação de servidores de mediação e definição de pares no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="2879c-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="2879c-118">Como proteger o Servidor de Mediação para troncos SIP</span><span class="sxs-lookup"><span data-stu-id="2879c-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="2879c-p104">Para fins de segurança, você deve configurar uma LAN virtual (VLAN) para cada conexão entre os dois roteadores VPN. O processo real para configurar uma VLAN varia de um fabricante de roteador para outro. Para detalhes, entre em contato com o fornecedor do seu roteador.</span><span class="sxs-lookup"><span data-stu-id="2879c-p104">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="2879c-122">É recomendável seguir estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="2879c-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="2879c-123">Configure uma VLAN (LAN virtual) entre o servidor de mediação e o roteador VPN na rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada).</span><span class="sxs-lookup"><span data-stu-id="2879c-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="2879c-124">Não permita que pacotes de transmissão ou multicast sejam transferidos do roteador para a VLAN.</span><span class="sxs-lookup"><span data-stu-id="2879c-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="2879c-125">Bloqueie todas as regras de roteamento que roteiam o tráfego do roteador para qualquer lugar, mas o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="2879c-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="2879c-126">Se você usa um servidor VPN, é recomendável seguir as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="2879c-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="2879c-127">Configurar uma VLAN entre o servidor VPN e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="2879c-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="2879c-128">Não permita que pacotes de transmissão ou multicast sejam transferidos do servidor VPN para a VLAN.</span><span class="sxs-lookup"><span data-stu-id="2879c-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="2879c-129">Bloqueie qualquer regra de roteamento que roteia o tráfego do servidor VPN para qualquer lugar, mas o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="2879c-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="2879c-130">Criptografe dados na VPN usando GRE (encapsulamento de roteamento genérico).</span><span class="sxs-lookup"><span data-stu-id="2879c-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

