---
title: 'Lync Server 2013: Componentes e topologias para o Servidor de Mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="de6a5-102">Componentes e topologias para o Servidor de Mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de6a5-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de6a5-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="de6a5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="de6a5-104">Este tópico descreve os componentes nos quais o servidor de mediação é dependente e as topologias nas quais o servidor de mediação pode ser implantado</span><span class="sxs-lookup"><span data-stu-id="de6a5-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="de6a5-105">Dependências</span><span class="sxs-lookup"><span data-stu-id="de6a5-105">Dependencies</span></span>

<span data-ttu-id="de6a5-106">O servidor de mediação tem as seguintes dependências:</span><span class="sxs-lookup"><span data-stu-id="de6a5-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="de6a5-107">**Profissional.**</span><span class="sxs-lookup"><span data-stu-id="de6a5-107">**Registrar.**</span></span> <span data-ttu-id="de6a5-108">Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="de6a5-108">Required.</span></span> <span data-ttu-id="de6a5-109">O registrador é o próximo nó para sinalizar nas interações do servidor de mediação com a rede do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de6a5-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="de6a5-110">Observe que o servidor de mediação pode ser posicionado em um servidor front-end juntamente com o registrador, além de ser instalado em um pool autônomo que consiste apenas em servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="de6a5-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="de6a5-111">O registrador é posicionado com um servidor de mediação e um gateway PSTN em um aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="de6a5-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="de6a5-112">**Monitoring Server.**</span><span class="sxs-lookup"><span data-stu-id="de6a5-112">**Monitoring Server.**</span></span> <span data-ttu-id="de6a5-113">Opcional, mas altamente recomendado.</span><span class="sxs-lookup"><span data-stu-id="de6a5-113">Optional but highly recommended.</span></span> <span data-ttu-id="de6a5-114">O Monitoring Server permite que o servidor de mediação Registre métricas de qualidade associadas a suas sessões de mídia.</span><span class="sxs-lookup"><span data-stu-id="de6a5-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="de6a5-115">**Servidor de borda.**</span><span class="sxs-lookup"><span data-stu-id="de6a5-115">**Edge Server.**</span></span> <span data-ttu-id="de6a5-116">Obrigatório para suporte externo a usuários.</span><span class="sxs-lookup"><span data-stu-id="de6a5-116">Required for external user support.</span></span> <span data-ttu-id="de6a5-117">O servidor de borda permite que o servidor de mediação interaja com os usuários que estão localizados atrás de um NAT ou firewall.</span><span class="sxs-lookup"><span data-stu-id="de6a5-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="de6a5-118">Topologia</span><span class="sxs-lookup"><span data-stu-id="de6a5-118">Topologies</span></span>

<span data-ttu-id="de6a5-119">O servidor de mediação do Lync Server 2013, por padrão, é posicionado com uma instância do registrador em um servidor de edição padrão, um pool de front-end ou um aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="de6a5-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="de6a5-120">Todos os servidores de mediação em um pool Front-end devem ser configurados de maneira idêntica.</span><span class="sxs-lookup"><span data-stu-id="de6a5-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="de6a5-121">Onde o desempenho é um problema, pode ser preferível implantar um ou mais servidores de mediação em um pool autônomo dedicado.</span><span class="sxs-lookup"><span data-stu-id="de6a5-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="de6a5-122">Ou, se você estiver implantando o entroncamento SIP, recomendamos que implante um pool autônomo do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="de6a5-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="de6a5-123">Se você implantar conexões SIP diretas em um gateway PSTN qualificado que ofereça suporte ao bypass de mídia e ao balanceamento de carga de DNS, um pool autônomo do servidor de mediação não será necessário.</span><span class="sxs-lookup"><span data-stu-id="de6a5-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="de6a5-124">Um pool autônomo do servidor de mediação não é necessário porque gateways qualificados são capazes de balanceamento de carga de DNS para um pool de servidores de mediação e podem receber tráfego de qualquer servidor de mediação em um pool.</span><span class="sxs-lookup"><span data-stu-id="de6a5-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="de6a5-125">Também recomendamos que você colocar o servidor de mediação em um pool de front-end quando tiver implantado PBXs de IP ou conectar-se a um controlador de borda de sessão (SBC) do provedor de servidor de telefonia pela Internet, contanto que qualquer uma das seguintes condições seja atendida:</span><span class="sxs-lookup"><span data-stu-id="de6a5-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="de6a5-126">O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.</span><span class="sxs-lookup"><span data-stu-id="de6a5-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="de6a5-127">O IP-PBX não é compatível com o bypass de mídia, mas o pool de front-end que hospeda o servidor de mediação pode manipular a transcodificação de voz para chamadas para as quais o bypass de mídia não se aplica.</span><span class="sxs-lookup"><span data-stu-id="de6a5-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="de6a5-128">Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de front-ends em que você deseja colocar o servidor de mediação pode manipular a carga.</span><span class="sxs-lookup"><span data-stu-id="de6a5-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="de6a5-129">Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="de6a5-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="de6a5-130">Para obter detalhes sobre qual topologia implantar, consulte [diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="de6a5-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="de6a5-131">A figura a seguir mostra uma topologia simples que consiste em dois locais conectados por um link WAN.</span><span class="sxs-lookup"><span data-stu-id="de6a5-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="de6a5-132">O servidor de mediação está posicionado com o registrador em um pool de front-end no site 1.</span><span class="sxs-lookup"><span data-stu-id="de6a5-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="de6a5-133">Os servidores de mediação no site 1 controlam o gateway PSTN no site 1 e o gateway no site 2.</span><span class="sxs-lookup"><span data-stu-id="de6a5-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="de6a5-134">Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até cada gateway PSTN (GW1 e GW2) têm bypass habilitado.</span><span class="sxs-lookup"><span data-stu-id="de6a5-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="de6a5-135">**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um gateway PSTN no Site 2**</span><span class="sxs-lookup"><span data-stu-id="de6a5-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="de6a5-136">![Topologia de voz com gateway de WAN servidor de mediação] (images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologia de voz com gateway de WAN servidor de mediação")</span><span class="sxs-lookup"><span data-stu-id="de6a5-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="de6a5-137">A próxima figura mostra uma topologia simples em que o servidor de mediação está posicionado com o registrador no pool de front-end no site 1 e tem uma conexão SIP direta com o IP-PBX no site 1.</span><span class="sxs-lookup"><span data-stu-id="de6a5-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="de6a5-138">Nesta figura, o servidor de mediação também controla um gateway PSTN no site 2.</span><span class="sxs-lookup"><span data-stu-id="de6a5-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="de6a5-139">Suponha que os usuários do Lync existam nos dois locais: 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="de6a5-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="de6a5-140">Além disso, presumir que o IP-PBX tem um processador de mídia associado que deve ser percorrido por toda a mídia originada dos pontos de extremidade do Lync antes de ser enviada a pontos de extremidade de mídia controlados pelo IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="de6a5-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="de6a5-141">Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até o PBX e o gateway PSTN têm o bypass de mídia habilitado.</span><span class="sxs-lookup"><span data-stu-id="de6a5-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="de6a5-142">**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um PBX no Site 2**</span><span class="sxs-lookup"><span data-stu-id="de6a5-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="de6a5-143">![Wan Topology Mediation Server PBX PBX] (images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Wan Topology Mediation Server PBX PBX")</span><span class="sxs-lookup"><span data-stu-id="de6a5-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="de6a5-144">Para obter detalhes sobre o planejamento de topologias PBX, consulte [diretrizes de implantação para o servidor de mediação no Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) e [Opções de implantação do SIP direto no Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span><span class="sxs-lookup"><span data-stu-id="de6a5-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="de6a5-145">O último número neste tópico mostra uma topologia em que o servidor de mediação está conectado ao SBC de um provedor de serviços de telefonia pela Internet.</span><span class="sxs-lookup"><span data-stu-id="de6a5-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="de6a5-146">Para obter detalhes sobre as topologias de tronco SIP, consulte [entroncamento SIP no Lync Server 2013](lync-server-2013-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="de6a5-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

