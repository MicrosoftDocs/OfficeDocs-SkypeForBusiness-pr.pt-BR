---
title: 'Lync Server 2013: definindo seus requisitos de controle de admissão de chamadas'
description: 'Lync Server 2013: definindo seus requisitos de controle de admissão de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9f675ac5811e0c0c1c23dc76ebb8b4525857836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545417"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="dd7a1-103">Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd7a1-103">Defining your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd7a1-104">_**Última modificação do tópico:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="dd7a1-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="dd7a1-p101">O planejamento do CAC (serviço de controle de admissão de chamadas) requer informações detalhadas sobre a topologia da rede da empresa. Para ajudar a planejar suas políticas do serviço de controle de admissão de chamadas, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="dd7a1-107">Identifique os hubs/backbones (chamados de *regiões de rede*) dentro de sua rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-107">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="dd7a1-108">Identifique os escritórios ou locais (chamados *sites de rede*) dentro de cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-108">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="dd7a1-109">Determine a rota de rede entre cada par de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-109">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="dd7a1-110">Determine os limites de largura de banda para cada link WAN.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-110">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd7a1-111">Os limites de largura de banda referem-se à quantidade de largura de banda em um link de WAN alocada para o tráfego de áudio/vídeo do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-111">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="dd7a1-112">Quando um link WAN é descrito como "largura de banda restrita", o link WAN tem um limite de largura de banda menor do que os picos de tráfego esperados pelo link.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-112">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="dd7a1-113">Identifique as subredes de IP que são atribuídas a cada site de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-113">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="dd7a1-114">Para explicar esses conceitos, usaremos a topologia de rede de exemplo mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-114">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="dd7a1-115">**Exemplo de topologia para o controle de admissão de chamada**</span><span class="sxs-lookup"><span data-stu-id="dd7a1-115">**Example topology for call admission control**</span></span>

<span data-ttu-id="dd7a1-116">![Exemplo de topologia de rede Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Exemplo de topologia de rede Litware Inc.")</span><span class="sxs-lookup"><span data-stu-id="dd7a1-116">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd7a1-p103">Todos os sites de rede estão associados a uma região de rede. Por exemplo, Portland, Reno e Albuquerque estão incluídos na região da América do Norte. Nessa figura, são mostrados apenas links WAN que têm políticas de CAC aplicadas, com limites de largura de banda. Os sites de rede de Chicago, Nova York e Detroit são mostrados dentro da região oval da América do Norte, porque eles não estão com restrições largura de banda e não exigem políticas de CAC.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="dd7a1-121">Os componentes da topologia neste exemplo são explicados nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-121">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="dd7a1-122">Para obter detalhes sobre como essa topologia foi planejada, incluindo os limites de largura de banda, consulte [exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="dd7a1-122">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="dd7a1-123">Identifique as regiões de rede</span><span class="sxs-lookup"><span data-stu-id="dd7a1-123">Identify Network Regions</span></span>

<span data-ttu-id="dd7a1-124">Uma região de rede representa um backbone de rede ou um hub da rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-124">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="dd7a1-p105">Um backbone ou hub de rede é uma parte da infraestrutura de rede do computador que interconecta diferentes partes da rede, fornecendo um caminho para a troca de informações entre diferentes LANs ou subredes. Um backbone pode interligar diversas redes de um pequeno local para uma área geográfica ampla. A capacidade do backbone é normalmente maior do que as redes que se conectam a ele.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="dd7a1-p106">Nossa topologia de exemplo tem três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém um conjunto de sites de rede (consulte a definição de sites de rede posteriormente neste tópico). Trabalhe com sua equipe de operações de rede para identificar as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="dd7a1-131">Associando um site central de cada região de rede</span><span class="sxs-lookup"><span data-stu-id="dd7a1-131">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="dd7a1-132">O CAC requer que um site central do Lync Server seja definido para cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-132">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="dd7a1-133">O site central é selecionado com a melhor conectividade de rede e maior largura de banda para todos os outros sites nessa região de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-133">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="dd7a1-134">O exemplo anterior da topologia de rede mostra três regiões de rede, cada uma com um site central que gerencia decisões do CAC.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-134">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="dd7a1-135">A partir do exemplo anterior, a associação apropriada é exibida na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-135">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd7a1-136">Os sites centrais não correspondem necessariamente aos sites de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-136">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="dd7a1-137">Nos exemplos nesta documentação, alguns sites centrais (Chicago, Londres e Pequim) compartilham os mesmos nomes que os sites de rede.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-137">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="dd7a1-138">No entanto, mesmo que um site central e um site de rede compartilhem o mesmo nome, o site central é um elemento da topologia do Lync Server, enquanto o local da rede é parte da rede geral na qual a topologia do Lync Server reside.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-138">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="dd7a1-139">Regiões de rede, sites centrais e sites de rede</span><span class="sxs-lookup"><span data-stu-id="dd7a1-139">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd7a1-140">Região de rede</span><span class="sxs-lookup"><span data-stu-id="dd7a1-140">Network Region</span></span></th>
<th><span data-ttu-id="dd7a1-141">Site central</span><span class="sxs-lookup"><span data-stu-id="dd7a1-141">Central Site</span></span></th>
<th><span data-ttu-id="dd7a1-142">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="dd7a1-142">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-143">América do Norte</span><span class="sxs-lookup"><span data-stu-id="dd7a1-143">North America</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="dd7a1-144">Chicago</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-145">Chicago</span><span class="sxs-lookup"><span data-stu-id="dd7a1-145">Chicago</span></span></p>
<p><span data-ttu-id="dd7a1-146">Nova York</span><span class="sxs-lookup"><span data-stu-id="dd7a1-146">New York</span></span></p>
<p><span data-ttu-id="dd7a1-147">Detroit</span><span class="sxs-lookup"><span data-stu-id="dd7a1-147">Detroit</span></span></p>
<p><span data-ttu-id="dd7a1-148">Portland</span><span class="sxs-lookup"><span data-stu-id="dd7a1-148">Portland</span></span></p>
<p><span data-ttu-id="dd7a1-149">Reno</span><span class="sxs-lookup"><span data-stu-id="dd7a1-149">Reno</span></span></p>
<p><span data-ttu-id="dd7a1-150">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="dd7a1-150">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd7a1-151">EMEA</span><span class="sxs-lookup"><span data-stu-id="dd7a1-151">EMEA</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-152">Londres</span><span class="sxs-lookup"><span data-stu-id="dd7a1-152">London</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-153">Londres</span><span class="sxs-lookup"><span data-stu-id="dd7a1-153">London</span></span></p>
<p><span data-ttu-id="dd7a1-154">Colônia</span><span class="sxs-lookup"><span data-stu-id="dd7a1-154">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-155">APAC</span><span class="sxs-lookup"><span data-stu-id="dd7a1-155">APAC</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-156">Pequim</span><span class="sxs-lookup"><span data-stu-id="dd7a1-156">Beijing</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-157">Pequim</span><span class="sxs-lookup"><span data-stu-id="dd7a1-157">Beijing</span></span></p>
<p><span data-ttu-id="dd7a1-158">Manila</span><span class="sxs-lookup"><span data-stu-id="dd7a1-158">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="dd7a1-159">Identifique os sites de rede</span><span class="sxs-lookup"><span data-stu-id="dd7a1-159">Identify Network Sites</span></span>

<span data-ttu-id="dd7a1-p109">Um site de rede representa um local onde a sua organização tem um espaço físico, por exemplo, um escritórios, um conjunto de edifícios ou um campus. Um espaço físico com uma LAN e conectividade WAN para outros sites é considerado um site de rede. Inicie o levantamento de todos os escritórios da organização. Em nosso exemplo de topologia, a região de rede da América do Norte consiste nos seguintes sites de rede: Nova York, Chicago, Detroit, Portland, Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="dd7a1-p110">Você deve associar cada site de rede a uma região de rede. Dependendo se o site de rede tem um link WAN restrito, uma política de largura de banda é associada ao site de rede. Para obter detalhes sobre políticas de CAC e a largura de banda que você alocar ao usá-las, consulte "Defina as políticas de largura de banda", posteriormente neste tópico. Para configurar o CAC, você deve associar os sites de rede às regiões de rede e criar políticas de alocação de largura de banda para aplicar às conexões de largura de banda restrita entre um determinado site ou região e conexões WAN entre locais e regiões.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="dd7a1-168">Identifique os links de rede</span><span class="sxs-lookup"><span data-stu-id="dd7a1-168">Identify Network Links</span></span>

<span data-ttu-id="dd7a1-p111">Os links de rede as representam conexões WAN físicas que vinculam sites e regiões diferentes. Em nosso exemplo de topologia, há dois links de rede regionais, cinco links de rede entre locais e regiões e um link de rede entre dois sites.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="dd7a1-171">Os dois links regionais estão entre América do Norte e EMEA, representado como NA-EMEA-LINK, e entre APAC e EMEA, representado como EMEA-APAC-LINK.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-171">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="dd7a1-p112">Os links de site são indicados por linhas que conectam Portland, Reno e Albuquerque à região da América do Norte, Manila à região APAC e Colônia à região EMEA. A linha entre Reno e Albuquerque mostra um link de rede direta entre esses dois sites.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="dd7a1-174">Defina as políticas de largura de banda</span><span class="sxs-lookup"><span data-stu-id="dd7a1-174">Define Bandwidth Policies</span></span>

<span data-ttu-id="dd7a1-p113">Trabalhe com sua equipe de operações de rede para determinar a quantidade de largura de banda WAN que está disponível para o tráfego de vídeo e áudio em tempo real entre os links WAN na organização. As políticas de largura de banda são geralmente aplicadas aos links WAN quando o uso de largura de banda é restrito, isso é, espera-se que ele seja maior do que a largura de banda que pode ser alocada para as modalidades de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="dd7a1-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="dd7a1-179">As políticas de largura de banda do CAC podem definir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dd7a1-179">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="dd7a1-180">Largura de banda total máxima alocada para áudio.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-180">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="dd7a1-181">Largura de banda total máxima alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-181">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="dd7a1-182">Largura de banda máxima alocada para uma única chamada de áudio (sessão).</span><span class="sxs-lookup"><span data-stu-id="dd7a1-182">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="dd7a1-183">Largura de banda máxima alocada para uma única chamada de vídeo (sessão).</span><span class="sxs-lookup"><span data-stu-id="dd7a1-183">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd7a1-184">Todos os valores de largura de banda do CAC representam os limites máximos de largura de banda <EM>unidirecional</EM>.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-184">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dd7a1-185">Os recursos de política de voz do Lync Server 2013 oferecem a capacidade de substituir as verificações de política de largura de banda para chamadas de entrada para o usuário (não para chamadas de saída que são colocadas pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="dd7a1-185">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="dd7a1-186">Depois da sessão ser estabelecida, o consumo de largura de banda será contabilizado com precisão.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-186">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="dd7a1-187">Essa configuração deve ser usada com moderação.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-187">This setting should be used sparingly.</span></span> <span data-ttu-id="dd7a1-188">Para obter detalhes, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-188">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="dd7a1-p116">Para otimizar a utilização de largura de banda com base por sessão, considere o tipo de codec de áudio e vídeo que será usado. Mais especificamente, evite alocar menos largura de banda para um codec que você espera que seja usado com frequência. Por outro lado, se você deseja impedir que a mídia use um codec que exija mais largura de banda, deverá definir a largura de banda máxima por sessão menor o suficiente para desencorajar tal uso. Para o áudio, nem todos os codecs estão disponíveis para cada cenário. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="dd7a1-194">As chamadas de áudio ponto a ponto entre os pontos de extremidade do Lync usarão RTAudio (8 kHz) ou RTAudio (16 kHz) quando você fatorar a largura de banda e a priorização de codecs.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-194">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="dd7a1-195">As chamadas de conferência entre os pontos de extremidade do Lync e o serviço de conferência A/V usarão G. 722 ou Siren.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-195">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="dd7a1-196">Chamadas para a rede telefônica pública comutada (PSTN) para ou a partir de pontos de extremidade do Lync usarão G. 711 ou RTAudio (8 kHz).</span><span class="sxs-lookup"><span data-stu-id="dd7a1-196">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="dd7a1-197">Use a tabela a seguir para ajudar a otimizar as configurações de largura de banda máxima por sessão.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-197">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="dd7a1-198">Utilização de largura de banda por codecs</span><span class="sxs-lookup"><span data-stu-id="dd7a1-198">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd7a1-199">Codec</span><span class="sxs-lookup"><span data-stu-id="dd7a1-199">Codec</span></span></th>
<th><span data-ttu-id="dd7a1-200">Requisito de largura de banda sem nenhuma FEC (correção de erro antecipada)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-200">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="dd7a1-201">Requisito de largura de banda com FEC (correção de erro antecipada)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-201">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-202">RTAudio (8 kHz)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-202">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-203">49,8 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-203">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-204">61,6 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-204">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd7a1-205">RTAudio (16 kHz)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-205">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-206">67 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-206">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-207">96 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-207">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-208">Siren</span><span class="sxs-lookup"><span data-stu-id="dd7a1-208">Siren</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-209">57,6 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-209">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-210">73,6 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-210">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd7a1-211">G. 711</span><span class="sxs-lookup"><span data-stu-id="dd7a1-211">G.711</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-212">102 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-212">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-213">166 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-213">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-214">G. 722</span><span class="sxs-lookup"><span data-stu-id="dd7a1-214">G.722</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-215">105,6 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-215">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-216">169,6 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-216">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd7a1-217">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-217">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-218">260 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-218">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-219">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dd7a1-219">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-220">RTVideo (VGA 30 fps)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-220">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-221">610 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-221">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-222">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dd7a1-222">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="dd7a1-p117">Os requisitos de largura de banda consideram a sobrecarga de conta para o seguinte: Ethernet II, IP, protocolo de datagrama de usuário (UDP), RTP (protocolo de transporte em tempo rea) e SRTP (protoco de controle de transporte em tempo real). Eles também incluem 10 kbps para sobrecarga RTCP.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="dd7a1-225">Os codecs G.722.1 e Siren são semelhantes, mas oferecem diferentes taxas de bits.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-225">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="dd7a1-226">G. 722, o codec padrão para a conferência do Lync Server, é completamente diferente dos codecs G. 722.1 e Siren.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-226">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="dd7a1-227">O codec Siren é usado no Lync Server nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="dd7a1-227">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="dd7a1-228">Quando a política de largura de banda está definida para que o G.722 seja usado.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-228">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="dd7a1-229">Se um cliente do Communications Server 2007 ou Communications Server 2007 R2 se conectar a um serviço de conferência do Lync Server (porque esses clientes não dão suporte ao codec G. 722).</span><span class="sxs-lookup"><span data-stu-id="dd7a1-229">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="dd7a1-230">Utilização de largura de banda por cenário</span><span class="sxs-lookup"><span data-stu-id="dd7a1-230">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd7a1-231">Cenário</span><span class="sxs-lookup"><span data-stu-id="dd7a1-231">Scenario</span></span></th>
<th><span data-ttu-id="dd7a1-232">Requisito de largura de banda otimizado por quantidade (kbps)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-232">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="dd7a1-233">Requisito de largura de banda para modo balanceado (kbps)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-233">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="dd7a1-234">Requisito de largura de banda otimizado por qualidade (kbps)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-234">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-235">Chamadas de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="dd7a1-235">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-236">45 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-236">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-237">62 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-237">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-238">91 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-238">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd7a1-239">Chamadas em conferência</span><span class="sxs-lookup"><span data-stu-id="dd7a1-239">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-240">53 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-240">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-241">101 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-241">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-242">165 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-242">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-243">Chamadas PSTN (entre o Lync 2013 e gateway PSTN, com bypass de mídia)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-243">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-245">97 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-245">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-246">161 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-246">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd7a1-247">Chamadas PSTN (entre o Lync 2013 e o servidor de mediação, sem bypass de mídia)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-247">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-248">45 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-248">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-249">97 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-249">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-250">161 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-250">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd7a1-251">Chamadas PSTN (entre o servidor de mediação e o gateway PSTN, sem bypass de mídia)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-251">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-253">97 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-253">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-254">161 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-254">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd7a1-255">Chamadas do Lync-Polycom</span><span class="sxs-lookup"><span data-stu-id="dd7a1-255">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-256">101 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-257">101 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-257">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="dd7a1-258">101 kbps</span><span class="sxs-lookup"><span data-stu-id="dd7a1-258">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="dd7a1-259">Identifique as subredes IP</span><span class="sxs-lookup"><span data-stu-id="dd7a1-259">Identify IP Subnets</span></span>

<span data-ttu-id="dd7a1-p118">Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas para cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho é significantemente simplificado.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="dd7a1-p119">Em nosso exemplo, o site de Nova York na região da América do Norte é atribuído às seguintes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Vamos supor que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, o computador obterá um endereço IP em um dos quatro intervalos reservados para Nova York, por exemplo, 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="dd7a1-265">As subredes IP especificadas durante a configuração de rede no servidor devem corresponder o formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-265">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="dd7a1-266">Um cliente do Lync usa seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-266">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="dd7a1-267">Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comprar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-267">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="dd7a1-268">Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-268">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="dd7a1-269">(Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará mesmo se você configurar as subredes virtuais.)</span><span class="sxs-lookup"><span data-stu-id="dd7a1-269">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="dd7a1-270">Por exemplo, se um cliente entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede IP 255.255.255.0, o Lync 2013 solicitará a ID de bypass associada à sub-rede 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-270">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="dd7a1-271">Se a subrede é definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="dd7a1-271">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="dd7a1-272">Portanto, é importante que o administrador insira as sub-redes exatamente conforme fornecido pelos clientes do Lync (que são provisionados com sub-redes durante a configuração de rede, de forma estática ou por DHCP).</span><span class="sxs-lookup"><span data-stu-id="dd7a1-272">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

