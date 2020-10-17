---
title: 'Lync Server 2013: opções de implantação do gateway PSTN'
description: 'Lync Server 2013: opções de implantação de gateway PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565587"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="6d99c-103">Opções de implantação de gateway PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d99c-103">PSTN gateway deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d99c-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6d99c-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="6d99c-105">Gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="6d99c-105">PSTN Gateways</span></span>

<span data-ttu-id="6d99c-106">Gateways PSTN são componentes de hardware de terceiros que convertem sinais e mídia entre a infraestrutura do Enterprise Voice e da PSTN, diretamente ou por meio de troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="6d99c-106">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="6d99c-107">Em qualquer uma das topologias, o gateway encerra o PSTN.</span><span class="sxs-lookup"><span data-stu-id="6d99c-107">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="6d99c-108">O gateway é isolado em sua própria sub-rede e está conectado à rede corporativa através do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="6d99c-108">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="6d99c-109">Normalmente, uma empresa com vários sites implantaria um ou mais gateways em cada site.</span><span class="sxs-lookup"><span data-stu-id="6d99c-109">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="6d99c-110">Os sites de filial podem se conectar à PSTN através de um gateway ou por meio de um aparelho de filial persistente, que combina o gateway e os servidores em uma única caixa.</span><span class="sxs-lookup"><span data-stu-id="6d99c-110">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="6d99c-111">Se os sites de filial usarem um gateway, tanto um servidor de registrador quanto de mediação serão necessários no site, a menos que o link WAN seja resiliente.</span><span class="sxs-lookup"><span data-stu-id="6d99c-111">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="6d99c-112">Um ou mais servidores de mediação, que são colocados em servidores front-end, podem encaminhar chamadas para um ou mais gateways em cada site.</span><span class="sxs-lookup"><span data-stu-id="6d99c-112">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="6d99c-113">Recomendamos que o registrador, o servidor de mediação e o gateway necessários no site sejam implantados como um aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="6d99c-113">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="6d99c-114">Determinar o número, o tamanho e o local de gateways PSTN é, talvez, a decisão mais importante e dispendiosa que você deve tomar ao planejar sua infraestrutura do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6d99c-114">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="6d99c-p103">Há várias perguntas a considerar. Tenha em mente que as respostas destas perguntas são interdependentes</span><span class="sxs-lookup"><span data-stu-id="6d99c-p103">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="6d99c-p104">Quantos gateways PSTN são necessários? A resposta depende do número de usuários, do número antecipado de chamadas simultâneas (carga de tráfego) e do número de sites (cada site precisa de um).</span><span class="sxs-lookup"><span data-stu-id="6d99c-p104">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="6d99c-p105">Qual deve ser o tamanho dos gateways? A resposta depende do número de usuários no site e da carga de tráfego.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p105">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="6d99c-p106">Onde os gateways devem ser localizados? A resposta depende em parte da topologia e em parte da distribuição geográfica de sua organização.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p106">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="6d99c-123">Você também deve considerar suas opções de topologia de gateway (para obter detalhes, consulte Topologias de Gateway posteriormente neste tópico).</span><span class="sxs-lookup"><span data-stu-id="6d99c-123">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="6d99c-124">Suporte de Tronco M:N</span><span class="sxs-lookup"><span data-stu-id="6d99c-124">M:N Trunk Support</span></span>

<span data-ttu-id="6d99c-125">Os servidores de mediação podem rotear chamadas por vários gateways, controladores de borda de sessão (SBCs) fornecidos por provedores de serviços de telefonia da Internet ou uma combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="6d99c-125">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="6d99c-126">Além disso, vários servidores de mediação no pool podem interagir com vários gateways.</span><span class="sxs-lookup"><span data-stu-id="6d99c-126">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="6d99c-127">A rota lógica definida entre um servidor de mediação e gateway é chamada de *tronco*.</span><span class="sxs-lookup"><span data-stu-id="6d99c-127">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="6d99c-128">Quando um usuário interno coloca uma chamada PSTN, a lógica de roteamento de saída no pool de front-ends escolhe o tronco a ser roteado para todas as combinações possíveis que podem estar disponíveis para roteamento de determinada chamada.</span><span class="sxs-lookup"><span data-stu-id="6d99c-128">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="6d99c-129">Com o balanceamento de carga DNS, se uma chamada falhar ao alcançar um gateway devido a um problema com um servidor de mediação específico no pool, a chamada será tentada novamente em um servidor de mediação alternativo no pool.</span><span class="sxs-lookup"><span data-stu-id="6d99c-129">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="6d99c-130">Para obter detalhes sobre o planejamento de vários gateways, consulte [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="6d99c-130">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="6d99c-131">Para obter detalhes sobre outros aprimoramentos de roteamento de saída, consulte [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="6d99c-131">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="6d99c-132">Topologias de gateway</span><span class="sxs-lookup"><span data-stu-id="6d99c-132">Gateway Topologies</span></span>

<span data-ttu-id="6d99c-133">Ao considerar as perguntas fundamentais da implantação de gateway, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6d99c-133">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="6d99c-134">Conte os sites nos quais você deseja fornecer conectividade PSTN usando o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6d99c-134">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="6d99c-135">Estime o tráfego em cada site (número de usuários e número médio de chamadas por hora, por usuário).</span><span class="sxs-lookup"><span data-stu-id="6d99c-135">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="6d99c-136">Implante um ou mais gateways em cada site a fim de manipular o tráfego antecipado.</span><span class="sxs-lookup"><span data-stu-id="6d99c-136">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="6d99c-137">A topologia de gateway distribuído resultante é exibida na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="6d99c-137">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="6d99c-138">**Topologia de gateway distribuída**</span><span class="sxs-lookup"><span data-stu-id="6d99c-138">**Distributed gateway topology**</span></span>

<span data-ttu-id="6d99c-139">![Diagrama de topologia de gateway distribuído](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagrama de topologia de gateway distribuído")</span><span class="sxs-lookup"><span data-stu-id="6d99c-139">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="6d99c-p108">Com essa topologia, as chamadas entre os trabalhadores em cada site e entre sites são todas roteadas através de sua intranet. As chamadas para o PSTN são roteadas sobre a rede IP da empresa até os gateways mais próximos do local dos números de destino. Mas e se sua organização suportar dezenas ou centenas ou até mesmo milhares de sites espalhados em um ou mais continentes, assim como fazem muitas instituições financeiras e outras grandes empresas? Nesses casos, a implantação de um gateway separado em cada site não é prática.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p108">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="6d99c-143">Para resolver esse problema, muitas empresas grandes preferem implantar um ou alguns sites centrais de telefonia grandes, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="6d99c-143">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="6d99c-144">**Topologia de site central de telefonia**</span><span class="sxs-lookup"><span data-stu-id="6d99c-144">**Telephony central site topology**</span></span>

<span data-ttu-id="6d99c-145">![Topologia de gateway do Data Center](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologia de gateway do Data Center")</span><span class="sxs-lookup"><span data-stu-id="6d99c-145">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="6d99c-146">Nessa topologia, vários gateways grandes o suficiente para acomodar a carga de usuário prevista são implantados em cada site central.</span><span class="sxs-lookup"><span data-stu-id="6d99c-146">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="6d99c-147">Todas as chamadas aos usuários na empresa são encaminhadas pelo provedor de serviço de telefonia da empresa a um site central.</span><span class="sxs-lookup"><span data-stu-id="6d99c-147">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="6d99c-148">A lógica de roteamento no site central determina se a chamada deve ser roteada pela intranet ou pela PSTN.</span><span class="sxs-lookup"><span data-stu-id="6d99c-148">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="6d99c-149">Local do gateway</span><span class="sxs-lookup"><span data-stu-id="6d99c-149">Gateway Location</span></span>

<span data-ttu-id="6d99c-p110">O local do gateway também pode determinar os tipos de gateways que você escolhe e como eles são configurados. Há dezenas de protocolos PSTN, nenhum em um padrão mundial. Se todos os seus gateways estiverem localizados em um único país/região, isso não será um problema, mas se você localizar os gateways em diversos países/regiões, cada um precisa estar configurado de acordo com os padrões de PSTN nesse país/região. Além disso, os gateways certificados para operação no, por exemplo, Canadá, talvez não sejam certificados na Índia, Brasil ou União Europeia.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p110">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="6d99c-154">Tamanho e número de gateways</span><span class="sxs-lookup"><span data-stu-id="6d99c-154">Gateway Size and Number</span></span>

<span data-ttu-id="6d99c-p111">Os gateways PSTN que a maioria das organizações considerará implantar variam com relação ao tamanho de 2 a 960 portas. (Há gateways ainda maiores, mas eles são usados principalmente pelos provedores de serviço de telefonia.) Ao estimar o número de portas exigido por sua organização, use as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="6d99c-p111">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="6d99c-p112">Organizações com uso leve de telefonia (uma chamada PSTN por usuário, por hora) deve alocar uma porta para cada 15 usuários. Por exemplo, se você tiver 20 usuários, precisará de um gateway com duas portas.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p112">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="6d99c-p113">Organizações com um uso moderado de telefonia (duas chamadas PSTN por usuário, por hora) deve alocar uma porta para cada 10 usuários. Por exemplo, se você tiver 100 usuários, precisará de um total de 10 portas alocadas entre um ou mais gateways.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p113">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="6d99c-p114">Organizações com uso pesado de telefonia (três ou mais chamadas PSTN por usuário, por hora) devem alocar uma porta para cada cinco usuários. Por exemplo, se você tiver 47.000 usuários, precisará de um total de 9.400 portas alocadas entre pelo menos 10 grandes gateways.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p114">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="6d99c-163">É possível adquirir portas adicionais à medida que o número de usuários ou quantidade de tráfego em sua organização aumenta.</span><span class="sxs-lookup"><span data-stu-id="6d99c-163">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="6d99c-p115">Para qualquer quantidade de usuários que você deve suportar, você tem a opção de implantar uma quantidade menor de gateways maiores ou menores. Como regra, recomenda-se um mínimo de dois gateways para uma organização a fim de manter a disponibilidade, caso um gateway falhe.</span><span class="sxs-lookup"><span data-stu-id="6d99c-p115">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="6d99c-166">Cada gateway PSTN que você implantar deve ter pelo menos um servidor de mediação correspondente.</span><span class="sxs-lookup"><span data-stu-id="6d99c-166">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

