---
title: 'Lync Server 2013: componente do servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b78a7903cb46ada3231d1d604ced2f8536699776
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="7e051-102">Componente do servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e051-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e051-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7e051-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7e051-104">Você deve implantar o Lync Server 2013, servidor de mediação se implantar a carga de trabalho do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7e051-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="7e051-105">Esta seção descreve a funcionalidade básica, as dependências, as topologias básicas e as diretrizes de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7e051-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="7e051-106">O servidor de mediação converte a sinalização e, em algumas configurações, mídia entre sua infraestrutura interna do Lync Server 2013, Enterprise Voice e um gateway PSTN (rede telefônica pública comutada) ou um tronco SIP (protocolo de iniciação de sessão).</span><span class="sxs-lookup"><span data-stu-id="7e051-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="7e051-107">No Lync Server 2013 Side, o servidor de mediação escuta em um único endereço de transporte de protocolo universal (MTLS) mútuo.</span><span class="sxs-lookup"><span data-stu-id="7e051-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="7e051-108">No lado do gateway, o Servidor de Mediação escuta em todas as portas de escuta associadas a troncos definidos no documento da topologia.</span><span class="sxs-lookup"><span data-stu-id="7e051-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="7e051-109">Todos os gateways qualificados devem oferecer suporte a TLS, mas também podem habilitar TCP.</span><span class="sxs-lookup"><span data-stu-id="7e051-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="7e051-110">TCP tem suporte em gateways que não oferecem suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="7e051-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="7e051-111">Se você também tiver um PBX (Public Branch Exchange) existente em seu ambiente, o servidor de mediação tratará as chamadas entre os usuários do Enterprise Voice e o PBX.</span><span class="sxs-lookup"><span data-stu-id="7e051-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="7e051-112">Se seu PBX for um IP-PBX, você poderá criar uma conexão SIP direta entre o PBX e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="7e051-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="7e051-113">Se seu PBX for um PBX TDM (Time Division multiplex), você também deverá implantar um gateway PSTN entre o servidor de mediação e o PBX.</span><span class="sxs-lookup"><span data-stu-id="7e051-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="7e051-114">Por padrão, o servidor de mediação é colocado com o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7e051-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="7e051-115">O servidor de mediação também pode ser implantado em um pool autônomo por motivos de desempenho, ou se você implantar o tronco SIP, caso em que o pool autônomo seja altamente recomendado.</span><span class="sxs-lookup"><span data-stu-id="7e051-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="7e051-116">Se você implantar conexões SIP diretas com um gateway PSTN qualificado que oferece suporte a bypass de mídia e balanceamento de carga DNS, um pool do Servidor de Mediação autônomo não será necessário.</span><span class="sxs-lookup"><span data-stu-id="7e051-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="7e051-117">Um pool de Servidores de Mediação autônomo não é necessário, pois os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool.</span><span class="sxs-lookup"><span data-stu-id="7e051-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="7e051-118">Também recomendamos que você posicione o Servidor de Mediação em um pool Front-End após implantar o IP-PBXs ou se conectar ao controlador de borda da sessão (SBC) de um Internet Telephony Server Provider, contanto que qualquer uma das seguintes condições seja atendida:</span><span class="sxs-lookup"><span data-stu-id="7e051-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="7e051-119">O IP-PBX ou SBC está configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode rotear tráfego uniformemente para todos os Servidores de Mediação no pool.</span><span class="sxs-lookup"><span data-stu-id="7e051-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="7e051-120">O IP-PBX não suporta bypass de mídia, mas o pool de front-ends que está hospedando o servidor de mediação pode lidar com a transcodificação de voz para chamadas às quais o bypass de mídia não se aplica.</span><span class="sxs-lookup"><span data-stu-id="7e051-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="7e051-121">Você pode usar a ferramenta de planejamento do Microsoft Lync Server 2013 para avaliar se o pool de front-ends onde você deseja colocar o servidor de mediação pode lidar com a carga.</span><span class="sxs-lookup"><span data-stu-id="7e051-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="7e051-122">Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="7e051-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="7e051-123">As principais funções do servidor de mediação são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="7e051-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="7e051-124">Criptografar e descriptografar SRTP no lado do Lync Server</span><span class="sxs-lookup"><span data-stu-id="7e051-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="7e051-125">Conversão do SIP em TCP (para gateways que não oferecem suporte a TLS) para SIP em MTLS (TLS mútuo)</span><span class="sxs-lookup"><span data-stu-id="7e051-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="7e051-126">Conversão de fluxos de mídia entre o Lync Server e o par de gateway do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="7e051-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="7e051-127">Conexão de clientes externos à rede com componentes internos de ICE, que permitem a passagem de NATs e firewalls.</span><span class="sxs-lookup"><span data-stu-id="7e051-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="7e051-128">Atuar como um intermediário para fluxos de chamadas aos quais um gateway não oferece suporte, como chamadas de trabalhadores remotos em um cliente do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="7e051-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="7e051-129">Em implantações que incluem tronco SIP, trabalho conjunto com o provedor de serviços de tronco SIP para oferecer suporte à PSTN, o que elimina a necessidade de um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="7e051-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="7e051-130">A figura a seguir mostra os protocolos de sinalização e de mídia usados pelo servidor de mediação ao se comunicar com um gateway PSTN básico e a infraestrutura Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7e051-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="7e051-131">**Protocolos de sinalização e a mídia usados pelo Servidor de Mediação**</span><span class="sxs-lookup"><span data-stu-id="7e051-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="7e051-132">![Diagrama de protocolos de servidor de mediação](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagrama de protocolos de servidor de mediação")</span><span class="sxs-lookup"><span data-stu-id="7e051-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e051-133">Se você estiver usando TCP ou RTP/RTCP (em vez de SRTP ou SRTCP) na rede entre o gateway PSTN e o servidor de mediação, recomendamos que você faça medidas para ajudar a garantir a segurança e a privacidade da rede.</span><span class="sxs-lookup"><span data-stu-id="7e051-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7e051-134">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7e051-134">In This Section</span></span>

  - [<span data-ttu-id="7e051-135">Tronco M:N no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e051-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="7e051-136">Controle de admissão de chamadas e servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e051-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="7e051-137">Enhanced 9-1-1 (E9-1-1) e servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e051-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="7e051-138">Bypass de mídia e servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e051-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="7e051-139">Componentes e topologias para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e051-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="7e051-140">Diretrizes de implantação para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e051-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

