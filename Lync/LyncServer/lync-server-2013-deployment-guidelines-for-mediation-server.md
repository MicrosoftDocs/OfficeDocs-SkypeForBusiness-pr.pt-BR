---
title: 'Lync Server 2013: diretrizes de implantação para o servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="d8142-102">Diretrizes de implantação para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8142-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8142-103">_**Tópico da última modificação:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="d8142-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="d8142-104">Este tópico descreve diretrizes de planejamento para a implantação do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="d8142-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="d8142-105">Depois de revisar essas diretrizes, recomendamos que você use a ferramenta de planejamento para criar e exibir possíveis topologias alternativas, que podem servir como modelos para o que a topologia personalizada final que você decidir implantar seria parecida com a aparência desejada.</span><span class="sxs-lookup"><span data-stu-id="d8142-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="d8142-106">Servidor de mediação autônomo ou posicionado?</span><span class="sxs-lookup"><span data-stu-id="d8142-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="d8142-107">O servidor de mediação é posicionado por padrão no servidor Standard Edition ou no servidor front-end em um pool de front-ends em sites centrais.</span><span class="sxs-lookup"><span data-stu-id="d8142-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="d8142-108">O número de chamadas PSTN (Rede Telefônica Pública Comutada) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:</span><span class="sxs-lookup"><span data-stu-id="d8142-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="d8142-109">O número de pares de gateway que o pool do servidor de mediação controla</span><span class="sxs-lookup"><span data-stu-id="d8142-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="d8142-110">Dos períodos de alto volume de tráfego por meio desses gateways</span><span class="sxs-lookup"><span data-stu-id="d8142-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="d8142-111">A porcentagem de chamadas que são chamadas cuja mídia ignora o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="d8142-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="d8142-112">Durante o planejamento, considere os requisitos de processamento de mídia das chamadas PSTN e das conferências A/V não configuradas para bypass de mídia, além do processamento necessário para lidar com as interações de sinalização em relação ao número de chamadas em horário de pico que precisam de suporte.</span><span class="sxs-lookup"><span data-stu-id="d8142-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="d8142-113">Se não houver CPU suficiente, você deve implantar um pool autônomo de servidores de mediação; e os gateways PSTN, PBXs IP e SBCs precisarão ser divididos em subconjuntos controlados pelos servidores de mediação posicionados em um pool e os servidores de mediação autônomos em um ou mais pools autônomos.</span><span class="sxs-lookup"><span data-stu-id="d8142-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="d8142-114">Se você implantou gateways PSTN, PBXs de IP ou controladores de borda de sessão (SBCs) que não são compatíveis com os recursos corretos para interagir com um pool de servidores de mediação, incluindo o seguinte, eles precisarão estar associados a um pool autônomo que consiste em de um servidor de mediação único:</span><span class="sxs-lookup"><span data-stu-id="d8142-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="d8142-115">Executar o balanceamento de carga de DNS (sistema de nomes de domínio) de camada de rede em servidores de mediação em um pool (ou de outra forma rotear uniformemente para todos os servidores de mediação em um pool)</span><span class="sxs-lookup"><span data-stu-id="d8142-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="d8142-116">Aceitar o tráfego de qualquer servidor de mediação em um pool</span><span class="sxs-lookup"><span data-stu-id="d8142-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="d8142-117">Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se colocar o servidor de mediação no seu pool de front-end pode manipular a carga.</span><span class="sxs-lookup"><span data-stu-id="d8142-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="d8142-118">Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="d8142-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="d8142-119">Considerações sobre o local central e o local da filial</span><span class="sxs-lookup"><span data-stu-id="d8142-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="d8142-120">Os servidores de mediação no site central podem ser usados para direcionar chamadas para IP-PBXs ou gateways PSTN em sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="d8142-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="d8142-121">No entanto, se você implantar troncos SIP, deve implantar um servidor de mediação no site em que cada tronco termina.</span><span class="sxs-lookup"><span data-stu-id="d8142-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="d8142-122">Ter um servidor de mediação no site central chamadas de rota para um IP-PBX ou um gateway PSTN em um site de filial não requer o uso do bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="d8142-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="d8142-123">No entanto, se você puder habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e, consequentemente, resultará em uma qualidade de mídia aprimorada porque o caminho da mídia não é mais necessário para acompanhar o caminho de sinalização.</span><span class="sxs-lookup"><span data-stu-id="d8142-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="d8142-124">O bypass de mídia também diminuirá a carga de processamento no pool.</span><span class="sxs-lookup"><span data-stu-id="d8142-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8142-125">O bypass de mídia não interoperará com cada gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="d8142-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="d8142-126">A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="d8142-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d8142-127">O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade aberta da comunicação <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>unificada – Lync Server em.</span><span class="sxs-lookup"><span data-stu-id="d8142-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="d8142-128">Se a resiliência do site de ramificação for necessária, um aparelho de ramificação sobreviventes ou uma combinação de um servidor front-end, um servidor de mediação e um gateway devem ser implantados no site da filial.</span><span class="sxs-lookup"><span data-stu-id="d8142-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="d8142-129">(A pressuposição da resiliência do site da ramificação é que a presença e a conferência não são resistentes no site.) Para obter orientação sobre o planejamento de site de filial para voz, consulte [planejando a resiliência de voz no site de filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="d8142-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="d8142-130">Para interações com um PBX IP, se o IP-PBX não suportar corretamente interações de mídia antigas com várias caixas de diálogo iniciais e interações RFC 3960, pode haver recorte das primeiras palavras da saudação para as chamadas recebidas dos pontos de extremidade IP-PBX para Lync.</span><span class="sxs-lookup"><span data-stu-id="d8142-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="d8142-131">Esse comportamento pode ser mais sério se um servidor de mediação em um site central estiver encaminhando chamadas para um PBX IP em que a rota termina em um site de filial, pois é necessária mais tempo para a sinalização ser concluída.</span><span class="sxs-lookup"><span data-stu-id="d8142-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="d8142-132">Se você tiver esse comportamento, a implantação de um servidor de mediação no site da filial é a única maneira de reduzir o recorte das primeiras palavras.</span><span class="sxs-lookup"><span data-stu-id="d8142-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="d8142-133">Por fim, se o seu site central tiver um PBX de TDM, ou se o seu PBX IP não eliminar a necessidade de um gateway PSTN, você deve implantar um gateway no servidor de mediação conectando o servidor de mediação da chamada e o PBX.</span><span class="sxs-lookup"><span data-stu-id="d8142-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8142-134">Para aprimorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores.</span><span class="sxs-lookup"><span data-stu-id="d8142-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="d8142-135">O RSS permite que pacotes de entrada sejam manipulados em paralelo por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="d8142-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="d8142-136">Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>Server" em.</span><span class="sxs-lookup"><span data-stu-id="d8142-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="d8142-137">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="d8142-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

