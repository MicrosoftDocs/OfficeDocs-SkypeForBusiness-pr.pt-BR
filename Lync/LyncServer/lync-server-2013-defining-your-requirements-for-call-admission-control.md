---
title: 'Lync Server 2013: Definindo seus requisitos de controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="2649d-102">Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2649d-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2649d-103">_**Tópico da última modificação:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="2649d-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="2649d-104">O planejamento de controle de admissão de chamadas (CAC) requer informações detalhadas sobre a topologia de rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="2649d-104">Planning for call admission control (CAC) requires detailed information about your enterprise network topology.</span></span> <span data-ttu-id="2649d-105">Para ajudar a planejar suas políticas de controle de admissão de chamadas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2649d-105">To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="2649d-106">Identifique os hubs/backbones (chamados de *regiões de rede*) dentro da sua rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="2649d-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="2649d-107">Identifique os escritórios ou locais (chamados de *sites de rede*) em cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="2649d-108">Determine a rota de rede entre todos os pares de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="2649d-109">Determine os limites de largura de banda para cada link de WAN.</span><span class="sxs-lookup"><span data-stu-id="2649d-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2649d-110">Os limites de largura de banda referem-se à quantidade de largura de banda de um link de WAN atribuída ao tráfego de voz e áudio/vídeo da empresa.</span><span class="sxs-lookup"><span data-stu-id="2649d-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="2649d-111">Quando um link de WAN é descrito como "largura de banda restringida", o link de WAN tem um limite de largura de banda menor do que o tráfego de pico esperado no link.</span><span class="sxs-lookup"><span data-stu-id="2649d-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="2649d-112">Identifique as sub-redes IP atribuídas a cada site de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="2649d-113">Para explicar esses conceitos, usaremos a topologia de rede de exemplo mostrada na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="2649d-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="2649d-114">**Exemplo de topologia para controle de admissão de chamadas**</span><span class="sxs-lookup"><span data-stu-id="2649d-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="2649d-115">![Litware Inc. exemplo de topologia de rede] (images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. exemplo de topologia de rede")</span><span class="sxs-lookup"><span data-stu-id="2649d-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2649d-116">Todos os sites de rede estão associados a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-116">All network sites are associated with a network region.</span></span> <span data-ttu-id="2649d-117">Por exemplo, Portland, Reno e Albuquerque estão incluídos na região da América do Norte.</span><span class="sxs-lookup"><span data-stu-id="2649d-117">For example, Portland, Reno, and Albuquerque are included in the North America region.</span></span> <span data-ttu-id="2649d-118">Nesta figura, somente links WAN que têm políticas de CAC aplicadas são mostrados, com limites de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="2649d-118">In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits.</span></span> <span data-ttu-id="2649d-119">Os sites de rede de Chicago, Nova York e Detroit são exibidos dentro da elipse da América do Norte, pois eles não são restringidos por largura de banda e, portanto, não exigem políticas do CAC.</span><span class="sxs-lookup"><span data-stu-id="2649d-119">The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="2649d-120">Os componentes deste exemplo de topologia são explicados nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="2649d-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="2649d-121">Para obter detalhes sobre como essa topologia era planejada, incluindo os limites de largura de banda, consulte [exemplo: reunir seus requisitos para o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="2649d-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="2649d-122">Identificar regiões de rede</span><span class="sxs-lookup"><span data-stu-id="2649d-122">Identify Network Regions</span></span>

<span data-ttu-id="2649d-123">Uma região de rede representa um backbone de rede ou um hub de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="2649d-124">Um backbone ou Hub de rede é uma parte da infraestrutura de rede de computador que interconecta partes diferentes da rede, fornecendo um caminho para a troca de informações entre diferentes LANs ou sub-redes.</span><span class="sxs-lookup"><span data-stu-id="2649d-124">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="2649d-125">Um backbone pode unir várias redes diferentes de um local pequeno para uma ampla área geográfica.</span><span class="sxs-lookup"><span data-stu-id="2649d-125">A backbone can tie together diverse networks from a small location to a wide geographic area.</span></span> <span data-ttu-id="2649d-126">A capacidade do backbone normalmente é maior do que a das redes conectadas a ele.</span><span class="sxs-lookup"><span data-stu-id="2649d-126">The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="2649d-127">Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="2649d-127">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="2649d-128">Uma região de rede contém um conjunto de sites de rede (consulte a definição de sites de rede mais adiante neste tópico).</span><span class="sxs-lookup"><span data-stu-id="2649d-128">A network region contains a collection of network sites (see the definition of network sites later in this topic).</span></span> <span data-ttu-id="2649d-129">Trabalhe com sua equipe de operações de rede para identificar suas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-129">Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="2649d-130">Associando um site central a cada região de rede</span><span class="sxs-lookup"><span data-stu-id="2649d-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="2649d-131">O CAC requer que um site central do Lync Server seja definido para cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="2649d-132">O site central é selecionado com a melhor conectividade de rede e largura de banda mais alta para todos os outros sites na região da rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="2649d-133">O exemplo anterior da topologia de rede mostra três regiões de rede, cada uma com um site central que gerencia decisões do CAC.</span><span class="sxs-lookup"><span data-stu-id="2649d-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="2649d-134">No exemplo anterior, a associação apropriada é mostrada na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="2649d-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2649d-135">Os sites centrais não correspondem necessariamente a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="2649d-136">Nos exemplos desta documentação, alguns sites centrais (Chicago, Londres e Pequim) compartilham o mesmo nome dos sites de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="2649d-137">No entanto, mesmo se um site central e um site de rede compartilharem o mesmo nome, o site central será um elemento da topologia do Lync Server, enquanto o site de rede faz parte da rede geral na qual a topologia do Lync Server reside.</span><span class="sxs-lookup"><span data-stu-id="2649d-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="2649d-138">Regiões de rede, sites centrais e sites de rede</span><span class="sxs-lookup"><span data-stu-id="2649d-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2649d-139">Região de rede</span><span class="sxs-lookup"><span data-stu-id="2649d-139">Network Region</span></span></th>
<th><span data-ttu-id="2649d-140">Local central</span><span class="sxs-lookup"><span data-stu-id="2649d-140">Central Site</span></span></th>
<th><span data-ttu-id="2649d-141">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="2649d-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2649d-142">América do Norte</span><span class="sxs-lookup"><span data-stu-id="2649d-142">North America</span></span></p></td>
<td><p><span data-ttu-id="2649d-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="2649d-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="2649d-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="2649d-144">Chicago</span></span></p>
<p><span data-ttu-id="2649d-145">Nova York</span><span class="sxs-lookup"><span data-stu-id="2649d-145">New York</span></span></p>
<p><span data-ttu-id="2649d-146">Detroit</span><span class="sxs-lookup"><span data-stu-id="2649d-146">Detroit</span></span></p>
<p><span data-ttu-id="2649d-147">Portland</span><span class="sxs-lookup"><span data-stu-id="2649d-147">Portland</span></span></p>
<p><span data-ttu-id="2649d-148">Reno</span><span class="sxs-lookup"><span data-stu-id="2649d-148">Reno</span></span></p>
<p><span data-ttu-id="2649d-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="2649d-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2649d-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="2649d-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="2649d-151">Londres</span><span class="sxs-lookup"><span data-stu-id="2649d-151">London</span></span></p></td>
<td><p><span data-ttu-id="2649d-152">Londres</span><span class="sxs-lookup"><span data-stu-id="2649d-152">London</span></span></p>
<p><span data-ttu-id="2649d-153">Cologne</span><span class="sxs-lookup"><span data-stu-id="2649d-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2649d-154">APAC</span><span class="sxs-lookup"><span data-stu-id="2649d-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="2649d-155">Pequim</span><span class="sxs-lookup"><span data-stu-id="2649d-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="2649d-156">Pequim</span><span class="sxs-lookup"><span data-stu-id="2649d-156">Beijing</span></span></p>
<p><span data-ttu-id="2649d-157">Manila</span><span class="sxs-lookup"><span data-stu-id="2649d-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="2649d-158">Identificar sites de rede</span><span class="sxs-lookup"><span data-stu-id="2649d-158">Identify Network Sites</span></span>

<span data-ttu-id="2649d-159">Um site de rede representa um local onde sua organização tem um local físico, por exemplo, escritórios, um conjunto de prédios ou um campus.</span><span class="sxs-lookup"><span data-stu-id="2649d-159">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus.</span></span> <span data-ttu-id="2649d-160">Um local físico com uma LAN e com conectividade de WAN a outros sites é considerado um site de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-160">A physical venue with a LAN and has WAN connectivity to other sites is considered a network site.</span></span> <span data-ttu-id="2649d-161">Comece inventariando todos os escritórios da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2649d-161">Start by inventorying all of your organization’s offices.</span></span> <span data-ttu-id="2649d-162">Na nossa topologia de exemplo, a região de rede da América do Norte consiste nos seguintes sites de rede: New York, Chicago, Detroit, Portland, Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="2649d-162">In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="2649d-163">Você deve associar todos os sites de rede a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-163">You must associate every network site with a network region.</span></span> <span data-ttu-id="2649d-164">Dependendo se o site de rede tem um link de WAN restrito, uma política de largura de banda é associada ao site de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-164">Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site.</span></span> <span data-ttu-id="2649d-165">Para obter detalhes sobre as políticas do CAC e a largura de banda que você atribuir usando-as, consulte "definir políticas de largura de banda" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2649d-165">For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic.</span></span> <span data-ttu-id="2649d-166">Para configurar o CAC, associe sites de rede com regiões de rede e, em seguida, crie políticas de alocação de largura de banda para aplicar às conexões restritas de largura de banda entre um determinado site ou região e as conexões WAN entre os sites e regiões.</span><span class="sxs-lookup"><span data-stu-id="2649d-166">To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="2649d-167">Identificar links de rede</span><span class="sxs-lookup"><span data-stu-id="2649d-167">Identify Network Links</span></span>

<span data-ttu-id="2649d-168">Links de rede representam conexões para a WAN física que vincula diferentes áreas e sites.</span><span class="sxs-lookup"><span data-stu-id="2649d-168">Network links represent connections to the physical WAN that links different regions and sites.</span></span> <span data-ttu-id="2649d-169">Na nossa topologia de exemplo, há dois links de rede regionais, cinco links de rede entre regiões e sites e um link de rede entre dois sites.</span><span class="sxs-lookup"><span data-stu-id="2649d-169">In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="2649d-170">Os dois links regionais estão entre a América do Norte e a EMEA, representados como NA-EMEA-LINK e entre a Ásia e a EMEA, representados como EMEA-Ásia-LINK.</span><span class="sxs-lookup"><span data-stu-id="2649d-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="2649d-171">Os links de site são indicados pelas linhas que conectam a Portland, Reno e Albuquerque à região da América do Norte, Manila à região da Ásia e Cologne à região da EMEA.</span><span class="sxs-lookup"><span data-stu-id="2649d-171">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region.</span></span> <span data-ttu-id="2649d-172">A linha entre Reno e Albuquerque mostra um link de rede direto entre esses dois sites.</span><span class="sxs-lookup"><span data-stu-id="2649d-172">The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="2649d-173">Definir políticas de largura de banda</span><span class="sxs-lookup"><span data-stu-id="2649d-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="2649d-174">Trabalhe com sua equipe de operações de rede para determinar Quanta largura de banda de WAN está disponível para tráfego de áudio e vídeo em tempo real nos links WAN de sua organização.</span><span class="sxs-lookup"><span data-stu-id="2649d-174">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization.</span></span> <span data-ttu-id="2649d-175">Geralmente, as políticas de largura de banda são aplicadas ao WAN links se o uso da largura de banda for restrito; ou seja, se ela deveria ser maior que a largura de banda que pode ser alocada para modalidades de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="2649d-175">Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="2649d-176">*Políticas de largura de banda* do CAC definem a largura de banda máxima que pode ser reservada para modalidades de áudio e vídeo em tempo real.</span><span class="sxs-lookup"><span data-stu-id="2649d-176">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities.</span></span> <span data-ttu-id="2649d-177">Como o CAC não limita a largura de banda de outro tráfego, ele não pode evitar outros tráfegos de dados, como uma transferência de arquivo grande, fluxo de música, desde o uso de toda a largura de banda da rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-177">Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="2649d-178">As políticas de largura de banda do CAC podem definir qualquer um dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="2649d-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="2649d-179">Largura de banda total máxima atribuída para áudio.</span><span class="sxs-lookup"><span data-stu-id="2649d-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="2649d-180">Largura de banda total máxima alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="2649d-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="2649d-181">Largura de banda máxima alocada para uma única chamada de áudio (sessão).</span><span class="sxs-lookup"><span data-stu-id="2649d-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="2649d-182">Largura de banda máxima alocada para uma única chamada de vídeo (sessão).</span><span class="sxs-lookup"><span data-stu-id="2649d-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2649d-183">Todos os valores de largura de banda <EM></EM> do CAC representam os limites de largura de banda unidirecionais</span><span class="sxs-lookup"><span data-stu-id="2649d-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2649d-184">Os recursos da política de voz do Lync Server 2013 fornecem a capacidade de substituir verificações de política de largura de banda para chamadas recebidas para o usuário (não para chamadas feitas pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="2649d-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="2649d-185">Depois que a sessão for estabelecida, o consumo de largura de banda será considerado com precisão.</span><span class="sxs-lookup"><span data-stu-id="2649d-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="2649d-186">Esta configuração deve ser usada com moderação.</span><span class="sxs-lookup"><span data-stu-id="2649d-186">This setting should be used sparingly.</span></span> <span data-ttu-id="2649d-187">Para obter detalhes, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="2649d-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="2649d-188">Para otimizar a utilização da largura de banda com base em cada sessão, considere o tipo de codecs de áudio e vídeo que será usado.</span><span class="sxs-lookup"><span data-stu-id="2649d-188">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used.</span></span> <span data-ttu-id="2649d-189">Em particular, evite alocar largura de banda insuficiente para um codec que você espera que seja usado com frequência.</span><span class="sxs-lookup"><span data-stu-id="2649d-189">In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently.</span></span> <span data-ttu-id="2649d-190">Por outro lado, se você quiser impedir que a mídia use um codec que exija mais largura de banda, deve definir a largura de banda máxima por sessão, o suficiente para desencorajar tal uso.</span><span class="sxs-lookup"><span data-stu-id="2649d-190">Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use.</span></span> <span data-ttu-id="2649d-191">Para áudio, nem todos os codecs estão disponíveis para todos os cenários.</span><span class="sxs-lookup"><span data-stu-id="2649d-191">For audio, not every codec is available for every scenario.</span></span> <span data-ttu-id="2649d-192">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2649d-192">For example:</span></span>

  - <span data-ttu-id="2649d-193">As chamadas de áudio ponto a ponto entre os pontos de extremidade do Lync usarão RTAudio (8kHz) ou RTAudio (16kHz) quando você fatorar a largura de banda e a priorização de codecs.</span><span class="sxs-lookup"><span data-stu-id="2649d-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="2649d-194">As chamadas em conferência entre os pontos de extremidade do Lync e o serviço de conferência A/V usarão G. 722 ou sirene.</span><span class="sxs-lookup"><span data-stu-id="2649d-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="2649d-195">As chamadas para a rede telefônica pública comutada (PSTN) para ou a partir de pontos de extremidade do Lync usarão G. 711 ou RTAudio (8kHz).</span><span class="sxs-lookup"><span data-stu-id="2649d-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="2649d-196">Use a tabela a seguir para ajudar a otimizar as configurações de largura de banda máxima por sessão.</span><span class="sxs-lookup"><span data-stu-id="2649d-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="2649d-197">Utilização de largura de banda por codecs</span><span class="sxs-lookup"><span data-stu-id="2649d-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2649d-198">Codec</span><span class="sxs-lookup"><span data-stu-id="2649d-198">Codec</span></span></th>
<th><span data-ttu-id="2649d-199">Requisitos de largura de banda sem correção de erro antecipado (FEC)</span><span class="sxs-lookup"><span data-stu-id="2649d-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="2649d-200">Requisitos de largura de banda com a correção de erro antecipada (FEC)</span><span class="sxs-lookup"><span data-stu-id="2649d-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2649d-201">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="2649d-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="2649d-202">49,8 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-203">61,6 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2649d-204">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="2649d-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="2649d-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2649d-207">Siren</span><span class="sxs-lookup"><span data-stu-id="2649d-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="2649d-208">57,6 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-209">73,6 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2649d-210">G.711</span><span class="sxs-lookup"><span data-stu-id="2649d-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="2649d-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2649d-213">G.722</span><span class="sxs-lookup"><span data-stu-id="2649d-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="2649d-214">105,6 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-215">169,6 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2649d-216">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="2649d-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="2649d-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-218">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="2649d-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2649d-219">RTVideo (VGA de 30 fps)</span><span class="sxs-lookup"><span data-stu-id="2649d-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="2649d-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-221">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="2649d-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2649d-222">Os requisitos de largura de banda levam em conta a sobrecarga para o seguinte: Ethernet II, IP, protocolo de datagrama de usuário (UDP), RTP (protocolo de transporte em tempo real) e SRTP (Secure real-time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="2649d-222">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol).</span></span> <span data-ttu-id="2649d-223">Eles também incluem 10 kbps para a sobrecarga RTCP.</span><span class="sxs-lookup"><span data-stu-id="2649d-223">They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="2649d-224">Os codecs G. 722.1 e sirene são semelhantes, mas oferecem tarifas de bit diferentes.</span><span class="sxs-lookup"><span data-stu-id="2649d-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="2649d-225">O G. 722, o codec padrão para a conferência do Lync Server, é completamente diferente dos codecs G. 722.1 e sirene.</span><span class="sxs-lookup"><span data-stu-id="2649d-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="2649d-226">O codec sirene é usado no Lync Server nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="2649d-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="2649d-227">Se a política de largura de banda estiver definida como muito baixa para G. 722 a ser usada.</span><span class="sxs-lookup"><span data-stu-id="2649d-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="2649d-228">Se um cliente do Communications Server 2007 ou Communications Server 2007 R2 se conectar a um serviço de conferência do Lync Server (pois esses clientes não dão suporte para o codec G. 722).</span><span class="sxs-lookup"><span data-stu-id="2649d-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="2649d-229">Utilização da largura de banda por cenário</span><span class="sxs-lookup"><span data-stu-id="2649d-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2649d-230">Cenário</span><span class="sxs-lookup"><span data-stu-id="2649d-230">Scenario</span></span></th>
<th><span data-ttu-id="2649d-231">Requisitos de largura de banda otimizados para quantidade (Kbps)</span><span class="sxs-lookup"><span data-stu-id="2649d-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="2649d-232">Requisitos de largura de banda para o modo balanceado (Kbps)</span><span class="sxs-lookup"><span data-stu-id="2649d-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="2649d-233">Requisitos de largura de banda otimizados para qualidade (Kbps)</span><span class="sxs-lookup"><span data-stu-id="2649d-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2649d-234">Chamadas de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="2649d-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="2649d-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2649d-238">Chamadas em conferência</span><span class="sxs-lookup"><span data-stu-id="2649d-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="2649d-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2649d-242">Chamadas PSTN (entre o Lync 2013 e o gateway PSTN com bypass de mídia)</span><span class="sxs-lookup"><span data-stu-id="2649d-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="2649d-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2649d-246">Chamadas PSTN (entre o Lync 2013 e o servidor de mediação, sem bypass de mídia)</span><span class="sxs-lookup"><span data-stu-id="2649d-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="2649d-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2649d-250">Chamadas PSTN (entre o servidor de mediação e o gateway PSTN sem bypass de mídia)</span><span class="sxs-lookup"><span data-stu-id="2649d-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="2649d-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2649d-254">Chamadas do Lync Polycom</span><span class="sxs-lookup"><span data-stu-id="2649d-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="2649d-255">101 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-256">101 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="2649d-257">101 kbps</span><span class="sxs-lookup"><span data-stu-id="2649d-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="2649d-258">Identifique as subredes IP</span><span class="sxs-lookup"><span data-stu-id="2649d-258">Identify IP Subnets</span></span>

<span data-ttu-id="2649d-259">Para cada site de rede, você precisará trabalhar com o administrador da rede para determinar quais sub-redes IP serão atribuídas a cada site de rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-259">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site.</span></span> <span data-ttu-id="2649d-260">Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.</span><span class="sxs-lookup"><span data-stu-id="2649d-260">If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="2649d-261">Em nosso exemplo, o site de Nova York na região da América do Norte recebe as seguintes sub-redes de IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span><span class="sxs-lookup"><span data-stu-id="2649d-261">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="2649d-262">Suponha que o Bob geralmente funcione no Detroit, vá para o escritório de Nova York para treinamento.</span><span class="sxs-lookup"><span data-stu-id="2649d-262">Suppose Bob, who typically works in Detroit, travels to the New York office for training.</span></span> <span data-ttu-id="2649d-263">Quando ele ligar o computador e se conectar à rede, o computador receberá um endereço IP em um dos quatro intervalos reservados para Nova York, por exemplo, 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="2649d-263">When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2649d-264">As sub-redes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato fornecido pelos computadores cliente para serem usadas corretamente para o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="2649d-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="2649d-265">Um cliente do Lync assume seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada.</span><span class="sxs-lookup"><span data-stu-id="2649d-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="2649d-266">Ao determinar a ID de bypass associada a cada cliente, o registrador irá comparar a lista de sub-redes IP associadas a cada site de rede em relação à sub-rede fornecida pelo cliente para uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="2649d-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="2649d-267">Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais.</span><span class="sxs-lookup"><span data-stu-id="2649d-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="2649d-268">(Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará mesmo se você configurar as subredes virtuais.)</span><span class="sxs-lookup"><span data-stu-id="2649d-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="2649d-269">Por exemplo, se um cliente entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede IP de 255.255.255.0, o Lync 2013 solicitará a ID de bypass associada à 172.29.81.0 de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2649d-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="2649d-270">Se a subrede for definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="2649d-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="2649d-271">Portanto, é importante que o administrador insira sub-redes exatamente conforme fornecido pelos clientes do Lync (que são provisionados com sub-redes durante a configuração de rede, de forma estática ou por DHCP.)</span><span class="sxs-lookup"><span data-stu-id="2649d-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

