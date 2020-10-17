---
title: 'Lync Server 2013: diretrizes de implantação para o servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4e627dfdc161093d07243e6598807f3ad91cab1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522708"
---
# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="adb84-102">Diretrizes de implantação para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adb84-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adb84-103">_**Última modificação do tópico:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="adb84-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="adb84-104">Este tópico descreve diretrizes de planejamento para a implantação do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="adb84-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="adb84-105">Depois de analisar essas diretrizes, recomendamos que você use a ferramenta de planejamento para criar e exibir possíveis topologias alternativas, que podem servir como modelos para o que a topologia personalizada final que você decidir implantar seria semelhante.</span><span class="sxs-lookup"><span data-stu-id="adb84-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="adb84-106">Servidor de mediação autônomo ou posicionado?</span><span class="sxs-lookup"><span data-stu-id="adb84-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="adb84-107">O Servidor de mediação é colocado por padrão no servidor Standard Edition ou no servidor Front-End em um pool de Front-End em locais centrais.</span><span class="sxs-lookup"><span data-stu-id="adb84-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="adb84-108">O número de chamadas de rede telefônica pública comutada (PSTN) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:</span><span class="sxs-lookup"><span data-stu-id="adb84-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="adb84-109">O número de pares de gateway que o pool do servidor de mediação controla</span><span class="sxs-lookup"><span data-stu-id="adb84-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="adb84-110">Os períodos de tráfego de alto volume por meio desses gateways</span><span class="sxs-lookup"><span data-stu-id="adb84-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="adb84-111">A porcentagem de chamadas que são chamadas cuja mídia ignora o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="adb84-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="adb84-112">Ao planejar, certifique-se de considerar os requisitos de processamento de mídia para chamadas PSTN e conferências A/V que não estão configuradas para bypass de mídia, bem como o processamento necessário para lidar com as interações de sinalização para o número de chamadas em tempo de ocupação que precisam ser suportadas.</span><span class="sxs-lookup"><span data-stu-id="adb84-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="adb84-113">Se não houver CPU suficiente, você deverá implantar um pool autônomo de servidores de mediação; e os gateways PSTN, IP-PBXs e SBCs precisarão ser divididos em subconjuntos controlados pelos servidores de mediação colocados em um pool e os servidores de mediação autônomos em um ou mais pools autônomos.</span><span class="sxs-lookup"><span data-stu-id="adb84-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="adb84-114">Se você implantou gateways PSTN, IP-PBXs ou controladores de borda de sessão (SBCs) que não dão suporte aos recursos corretos para interagir com um pool de servidores de mediação, incluindo o seguinte, então eles precisarão ser associados a um pool autônomo que consiste em um único servidor de mediação:</span><span class="sxs-lookup"><span data-stu-id="adb84-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="adb84-115">Executar o balanceamento de carga do DNS (sistema de nomes de domínio) da camada de rede nos servidores de mediação em um pool (ou, caso contrário, rotear o tráfego uniformemente para todos os servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="adb84-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="adb84-116">Aceitar tráfego de qualquer servidor de mediação em um pool</span><span class="sxs-lookup"><span data-stu-id="adb84-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="adb84-117">Você pode usar a ferramenta de planejamento do Microsoft Lync Server 2013 para avaliar se a colocação do servidor de mediação com seu pool de front-ends pode lidar com a carga.</span><span class="sxs-lookup"><span data-stu-id="adb84-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="adb84-118">Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="adb84-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="adb84-119">Considerações sobre o site central e site de filial</span><span class="sxs-lookup"><span data-stu-id="adb84-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="adb84-p105">Os servidores de mediação no site central podem ser usados para rotear chamadas para gateways IP PBXs ou PSTN em sites de flial. Se você implantar os troncos SIP, no entanto, é necessário implantar um servidor de mediação no site onde termina cada tronco. Com um servidor de mediação no site central para rotear chamadas a um gateway PBX IP ou PSTN de uma filial não requer o uso de bypass de mídia. No entanto, se você pode ativar o bypass de mídia, isso irá reduzir a latência do caminho de mídia e, conseqüentemente, resultar em uma melhor qualidade mídia, porque o caminho de mídia não é mais necessário para seguir o caminho de sinalização. O bypass de mídia também irá diminuir a carga de processamento no pool.</span><span class="sxs-lookup"><span data-stu-id="adb84-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adb84-125">O desvio de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="adb84-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="adb84-126">A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="adb84-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="adb84-127">O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações unificativas – Lync Server em <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A> .</span><span class="sxs-lookup"><span data-stu-id="adb84-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="adb84-128">Se a flexibilidade do site de filial for necessária, um Aparelho de Filial Persistente ou uma combinação de um servidor Front-End, um servidor de mediação e um gateway devem ser implantados na filial.</span><span class="sxs-lookup"><span data-stu-id="adb84-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="adb84-129">(A pressuposição da resiliência do site de filial é que a presença e a conferência não são resistentes no site.) Para obter orientação sobre o planejamento do site de filial para voz, consulte [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="adb84-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="adb84-130">Para interações com um IP-PBX, se o IP-PBX não suportar corretamente interações de mídias antigas com várias caixas de diálogo anteriores e interações RFC 3960, pode haver recorte das primeiras palavras da saudação para chamadas de entrada dos pontos de extremidade IP-PBX para Lync.</span><span class="sxs-lookup"><span data-stu-id="adb84-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="adb84-131">Esse comportamento pode ser mais grave se um servidor de mediação em um site central estiver roteando chamadas a um PBX IP onde a rota termina em um site de filial, porque é necessário mais tempo para concluir a sinalização.</span><span class="sxs-lookup"><span data-stu-id="adb84-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="adb84-132">Se você enfrentar esse comportamento, a implantação de um servidor de mediação no site de filial é a única maneira de reduzir o recorte das primeiras palavras.</span><span class="sxs-lookup"><span data-stu-id="adb84-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="adb84-133">Finalmente, se o site central tiver um PBX TDM ou se o IP-PBX não elimina a necessidade de um gateway PSTN, você deve implantar um gateway na rota de chamada que conecta o servidor de mediação e o PBX.</span><span class="sxs-lookup"><span data-stu-id="adb84-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="adb84-134">Para melhorar o desempenho de mídia do servidor de mediação autônomo, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede nesses servidores.</span><span class="sxs-lookup"><span data-stu-id="adb84-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="adb84-135">O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor.</span><span class="sxs-lookup"><span data-stu-id="adb84-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="adb84-136">Para obter detalhes, consulte "aprimoramentos de redimensionamento no lado do recebimento no Windows Server" em <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="adb84-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="adb84-137">Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="adb84-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

