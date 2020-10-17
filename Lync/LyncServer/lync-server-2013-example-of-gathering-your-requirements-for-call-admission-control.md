---
title: Exemplo de coleta de seus requisitos para controle de admissão de chamadas
description: Exemplo de coleta de seus requisitos para controle de admissão de chamadas.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c0b450070bda62c2610d98cfff8c8cd16ad2af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564937"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="ed800-103">Exemplo: coletando seus requisitos para controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed800-103">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed800-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ed800-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ed800-p101">Este exemplo mostra como planejar e implementar o CAC (controle de admissão de chamadas). Em um alto nível, isso consiste nas seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="ed800-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="ed800-107">Identificar todos os seus hubs e backbones de rede (conhecidos como *regiões de rede*).</span><span class="sxs-lookup"><span data-stu-id="ed800-107">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="ed800-108">Identifique o site central do Lync Server que gerenciará o CAC para cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-108">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="ed800-109">Identificar e definir os *sites de rede* conectados a cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-109">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="ed800-110">Para cada local de rede cuja conexão com a WAN é restrita à largura de banda, descreva a capacidade de largura de banda da conexão WAN e os limites de largura de banda que para o administrador de rede definiu para o tráfego de mídia do Lync Server, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="ed800-110">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="ed800-111">Não é necessário incluir sites cuja conexão com a WAN não sofra restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="ed800-111">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="ed800-112">Associe cada sub-rede em sua rede a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-112">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="ed800-113">Mapeie os links entre as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-113">Map the links between the network regions.</span></span> <span data-ttu-id="ed800-114">Para cada link, descreva sua capacidade de largura de banda e quaisquer limites que o administrador de rede colocou no tráfego de mídia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed800-114">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="ed800-115">Defina uma rota entre cada par de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-115">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="ed800-116">Colete as informações necessárias</span><span class="sxs-lookup"><span data-stu-id="ed800-116">Gather the Required Information</span></span>

<span data-ttu-id="ed800-117">Para se preparar para o controle de admissão de chamada, colete as informações descritas nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ed800-117">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="ed800-p104">Identifique suas regiões de rede. Uma região de rede representa um backbone de rede ou um hub de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="ed800-p105">Um backbone de rede ou um hub de rede faz parte da infraestrutura de rede do computador que interconecta diversas peças da rede, fornecendo um caminho para a troca de informações entre LANs ou sub-redes diferentes. Um backbone pode unir diversas redes, de um pequeno local até uma área geográfica ampla. A capacidade do backbone é normalmente superior a da rede conectada a ele.</span><span class="sxs-lookup"><span data-stu-id="ed800-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="ed800-p106">Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém uma coleção de sites de rede. Trabalhe com seu administrador de rede para definir as regiões de rede para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ed800-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="ed800-126">Identifique o site central associado a cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-126">Identify each network region’s associated central site.</span></span> <span data-ttu-id="ed800-127">Um site central contém pelo menos um servidor front-end e é a implantação do Lync Server que gerenciará o CAC para todo o tráfego de mídia que passar pela conexão WAN da região de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-127">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="ed800-128">**Um exemplo de rede de empresa dividida em três regiões de rede**</span><span class="sxs-lookup"><span data-stu-id="ed800-128">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="ed800-129">![Exemplo de topologia de rede com 3 regiões de rede](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Exemplo de topologia de rede com 3 regiões de rede")</span><span class="sxs-lookup"><span data-stu-id="ed800-129">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ed800-130">Uma rede MPLS (Multiprotocol Label Switching) deve ser representada como uma região de rede na qual cada local geográfico tem um site de rede correspondente.</span><span class="sxs-lookup"><span data-stu-id="ed800-130">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="ed800-131">Para obter detalhes, consulte o tópico "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">controle de admissão de chamadas em uma rede MPLS com Lync Server 2013</A>" na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ed800-131">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="ed800-132">Na topologia de rede de exemplo anterior, há três regiões de rede, cada uma com um site central do Lync Server que gerencia o CAC.</span><span class="sxs-lookup"><span data-stu-id="ed800-132">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="ed800-133">O site central apropriado para uma região de rede é escolhido pela proximidade geográfica.</span><span class="sxs-lookup"><span data-stu-id="ed800-133">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="ed800-134">Como o tráfego de mídia será o mais intenso nas regiões de rede, a propriedade por proximidade geográfica o tornará autocontido e continuará funcionando mesmo se outros sites centrais ficarem indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="ed800-134">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="ed800-135">Neste exemplo, uma implantação do Lync Server chamada Chicago é o site central da região da América do Norte.</span><span class="sxs-lookup"><span data-stu-id="ed800-135">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="ed800-136">Todos os usuários do Lync na América do Norte estão hospedados em servidores da implantação de Chicago.</span><span class="sxs-lookup"><span data-stu-id="ed800-136">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="ed800-137">A tabela a seguir mostra os sites centrais de todas as três regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-137">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="ed800-138">Regiões de rede e seus sites centrais associados</span><span class="sxs-lookup"><span data-stu-id="ed800-138">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-139">Região de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-139">Network Region</span></span></th>
    <th><span data-ttu-id="ed800-140">Site central</span><span class="sxs-lookup"><span data-stu-id="ed800-140">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-141">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-141">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-142">Chicago</span><span class="sxs-lookup"><span data-stu-id="ed800-142">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-143">EMEA</span><span class="sxs-lookup"><span data-stu-id="ed800-143">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="ed800-144">Londres</span><span class="sxs-lookup"><span data-stu-id="ed800-144">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-145">APAC</span><span class="sxs-lookup"><span data-stu-id="ed800-145">APAC</span></span></p></td>
    <td><p><span data-ttu-id="ed800-146">Pequim</span><span class="sxs-lookup"><span data-stu-id="ed800-146">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ed800-147">Dependendo da sua topologia do Lync Server, o mesmo site central pode ser atribuído a várias regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-147">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="ed800-p111">Para cada região de rede, identifique todos os sites de rede (escritórios ou locais) cujas conexões WAN não sofrem restrições de largura de banda. Como esses sites não sofrem restrições de largura de banda, não é necessário aplicar as políticas de largura de banda de CAC neles.</span><span class="sxs-lookup"><span data-stu-id="ed800-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="ed800-150">No exemplo exibido na tabela abaixo, três sites de rede não têm links de WAN com restrição de largura de banda: Nova York, Chicago e Detroit.</span><span class="sxs-lookup"><span data-stu-id="ed800-150">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="ed800-151">Sites de rede sem restrições de largura de banda de WAN</span><span class="sxs-lookup"><span data-stu-id="ed800-151">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-152">Site de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-152">Network Site</span></span></th>
    <th><span data-ttu-id="ed800-153">Região de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-153">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-154">Nova York</span><span class="sxs-lookup"><span data-stu-id="ed800-154">New York</span></span></p></td>
    <td><p><span data-ttu-id="ed800-155">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-155">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-156">Chicago</span><span class="sxs-lookup"><span data-stu-id="ed800-156">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="ed800-157">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-157">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-158">Detroit</span><span class="sxs-lookup"><span data-stu-id="ed800-158">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="ed800-159">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-159">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="ed800-160">Para cada região de rede, identifique todos os sites de rede que se conectam à região de rede por meio de links de WAN com restrição de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="ed800-160">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="ed800-161">Para garantir a qualidade de áudio e vídeo, é recomendável que esses locais de rede com restrição de largura de banda tenham as WANs monitoradas e tenham políticas de largura de banda de CAC que limitem o tráfego de mídia (voz ou vídeo) de e para a região de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-161">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="ed800-162">No exemplo exibido na tabela abaixo, há três sites de rede com restrição de largura de banda de WAN: Portland, Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="ed800-162">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="ed800-163">Sites de rede com restrições de largura de banda de WAN</span><span class="sxs-lookup"><span data-stu-id="ed800-163">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-164">Site de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-164">Network Site</span></span></th>
    <th><span data-ttu-id="ed800-165">Região de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-165">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-166">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="ed800-166">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="ed800-167">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-167">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-168">Reno</span><span class="sxs-lookup"><span data-stu-id="ed800-168">Reno</span></span></p></td>
    <td><p><span data-ttu-id="ed800-169">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-169">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-170">Portland</span><span class="sxs-lookup"><span data-stu-id="ed800-170">Portland</span></span></p></td>
    <td><p><span data-ttu-id="ed800-171">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-171">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="ed800-172">**Região de rede de CAC América do Norte com três sites de rede sem restrição de largura de banda (Chicago, Nova York e Detroit) e três sites de rede com restrição de largura de banda de WAN (Portland, Reno e Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="ed800-172">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="ed800-173">![Exemplo de sites de rede restritos pela largura de banda de WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Exemplo de sites de rede restritos pela largura de banda de WAN")</span><span class="sxs-lookup"><span data-stu-id="ed800-173">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="ed800-174">Para cada link de WAN com restrição de largura de banda, determine o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ed800-174">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="ed800-175">Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas.</span><span class="sxs-lookup"><span data-stu-id="ed800-175">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="ed800-176">Se uma nova sessão de áudio fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed800-176">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="ed800-p113">Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed800-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="ed800-179">Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas.</span><span class="sxs-lookup"><span data-stu-id="ed800-179">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="ed800-180">Se uma nova sessão de vídeo fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed800-180">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="ed800-p115">Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed800-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="ed800-183">Sites de rede com informações sobre restrição de largura de banda de WAN (largura de banda em kbps)</span><span class="sxs-lookup"><span data-stu-id="ed800-183">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-184">Site de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-184">Network Site</span></span></th>
    <th><span data-ttu-id="ed800-185">Região de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-185">Network Region</span></span></th>
    <th><span data-ttu-id="ed800-186">Limite de BW</span><span class="sxs-lookup"><span data-stu-id="ed800-186">BW Limit</span></span></th>
    <th><span data-ttu-id="ed800-187">Limite de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-187">Audio Limit</span></span></th>
    <th><span data-ttu-id="ed800-188">Limite de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-188">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="ed800-189">Limite de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-189">Video Limit</span></span></th>
    <th><span data-ttu-id="ed800-190">Limite de sessão de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-190">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-191">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="ed800-191">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="ed800-192">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-192">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-193">5.000</span><span class="sxs-lookup"><span data-stu-id="ed800-193">5,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-194">2,000</span><span class="sxs-lookup"><span data-stu-id="ed800-194">2,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-195">175</span><span class="sxs-lookup"><span data-stu-id="ed800-195">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-196">1.400</span><span class="sxs-lookup"><span data-stu-id="ed800-196">1,400</span></span></p></td>
    <td><p><span data-ttu-id="ed800-197">700</span><span class="sxs-lookup"><span data-stu-id="ed800-197">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-198">Reno</span><span class="sxs-lookup"><span data-stu-id="ed800-198">Reno</span></span></p></td>
    <td><p><span data-ttu-id="ed800-199">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-199">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-200">10.000</span><span class="sxs-lookup"><span data-stu-id="ed800-200">10,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-201">4.000</span><span class="sxs-lookup"><span data-stu-id="ed800-201">4,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-202">175</span><span class="sxs-lookup"><span data-stu-id="ed800-202">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-203">2.800</span><span class="sxs-lookup"><span data-stu-id="ed800-203">2,800</span></span></p></td>
    <td><p><span data-ttu-id="ed800-204">700</span><span class="sxs-lookup"><span data-stu-id="ed800-204">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-205">Portland</span><span class="sxs-lookup"><span data-stu-id="ed800-205">Portland</span></span></p></td>
    <td><p><span data-ttu-id="ed800-206">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-206">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-207">5.000</span><span class="sxs-lookup"><span data-stu-id="ed800-207">5,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-208">4.000</span><span class="sxs-lookup"><span data-stu-id="ed800-208">4,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-209">175</span><span class="sxs-lookup"><span data-stu-id="ed800-209">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-210">2.800</span><span class="sxs-lookup"><span data-stu-id="ed800-210">2,800</span></span></p></td>
    <td><p><span data-ttu-id="ed800-211">700</span><span class="sxs-lookup"><span data-stu-id="ed800-211">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-212">Nova York</span><span class="sxs-lookup"><span data-stu-id="ed800-212">New York</span></span></p></td>
    <td><p><span data-ttu-id="ed800-213">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-213">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-214">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-215">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-216">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-217">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-217">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-218">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-218">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-219">Chicago</span><span class="sxs-lookup"><span data-stu-id="ed800-219">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="ed800-220">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-220">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-221">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-222">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-223">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-224">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-224">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-225">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-225">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-226">Detroit</span><span class="sxs-lookup"><span data-stu-id="ed800-226">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="ed800-227">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-227">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-228">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-229">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-230">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-231">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-231">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-232">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-232">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="ed800-233">Para cada sub-rede em sua rede, especifique seu site de rede associado.</span><span class="sxs-lookup"><span data-stu-id="ed800-233">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="ed800-p116">Cada sub-rede em sua rede precisa estar associada a um site de rede, mesmo se o site de rede não sofrer restrição de largura de banda. Isso é devido ao controle de admissão de chamada usar as informações da sub-rede para determinar em qual site de rede um ponto de extremidade está localizado. Quando os locais de ambas as partes na sessão são determinados, o controle de admissão de chamada pode determinar se há largura de banda suficiente para estabelecer uma chamada. Quando uma sessão é estabelecida sobre um link que não possui limites de largura de banda, um alerta é gerado.</span><span class="sxs-lookup"><span data-stu-id="ed800-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="ed800-238">Se você implantar os Servidores de Borda de Áudio/Vídeo, os endereços IP públicos de cada Servidor de Borda deverão ser associados ao site externo no qual o Servidor de Borda está implantado.</span><span class="sxs-lookup"><span data-stu-id="ed800-238">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="ed800-239">Cada endereço IP público do Servidor de Borda A/V precisa ser adicionado às suas configurações de rede como uma sub-rede com a máscara de sub-rede de 32.</span><span class="sxs-lookup"><span data-stu-id="ed800-239">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="ed800-240">Por exemplo, se você implantar os Servidores de Borda A/V em Chicago, para cada endereço IP externo desses servidores, crie uma sub-rede com uma máscara de sub-rede de 32 e associe o site de rede Chicago a essas sub-redes.</span><span class="sxs-lookup"><span data-stu-id="ed800-240">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="ed800-241">Para obter detalhes sobre endereços IP públicos, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determine external A/V Firewall and Port Requirements for Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ed800-241">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ed800-p118">Um alerta de KHI (Key Health Indicator) é acionado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede ou a sub-rede que inclui os endereços IP não está associada a um site de rede. Esse alerta não será acionado novamente durante um período de oito horas. Veja a seguir as informações relevantes do alerta e um exemplo:</span><span class="sxs-lookup"><span data-stu-id="ed800-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="ed800-245"><STRONG>Fonte:</STRONG> Serviço de política de largura de banda CS (núcleo)</span><span class="sxs-lookup"><span data-stu-id="ed800-245"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="ed800-246"><STRONG>Número do evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="ed800-246"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="ed800-247"><STRONG>Nível:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="ed800-247"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="ed800-248"><STRONG>Descrição:</STRONG> As sub-redes para os seguintes endereços IP: a &lt; lista de endereços IP &gt; não estão configuradas ou as sub-redes não estão associadas a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-248"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="ed800-249"><STRONG>Causa:</STRONG> As sub-redes dos endereços IP correspondentes estão ausentes nas definições de configuração de rede ou as sub-redes não estão associadas a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-249"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="ed800-250"><STRONG>Resolução:</STRONG> Adicione sub-redes correspondentes à lista anterior de endereços IP nas definições de configuração de rede e associe todas as sub-redes a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-250"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="ed800-p119">Por exemplo, a lista de endereços IP do alerta especifica 10.121.248.226 e 10.121.249.20. Esses dois endereços IP não estão associados a uma sub-rede ou a sub-rede a qual eles estão associados não pertence a um site de rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes desses endereços, será possível resolver esse problema da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ed800-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="ed800-253">Certifique-se de que o endereço IP 10.121.248.226 esteja associado à sub-rede 10.121.248.0/24 e o endereço IP 10.121.249.20 esteja associado à sub-rede 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="ed800-253">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ed800-254">Certifique-se de que cada uma das sub-redes 10.121.248.0/24 e 10.121.249.0/24 esteja associada a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-254">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="ed800-255">Sites de rede e sub-redes associadas (largura de banda em kbps)</span><span class="sxs-lookup"><span data-stu-id="ed800-255">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-256">Site de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-256">Network Site</span></span></th>
    <th><span data-ttu-id="ed800-257">Região de rede</span><span class="sxs-lookup"><span data-stu-id="ed800-257">Network Region</span></span></th>
    <th><span data-ttu-id="ed800-258">Limite de BW</span><span class="sxs-lookup"><span data-stu-id="ed800-258">BW Limit</span></span></th>
    <th><span data-ttu-id="ed800-259">Limite de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-259">Audio Limit</span></span></th>
    <th><span data-ttu-id="ed800-260">Limite de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-260">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="ed800-261">Limite de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-261">Video Limit</span></span></th>
    <th><span data-ttu-id="ed800-262">Limite de sessão de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-262">Video Session Limit</span></span></th>
    <th><span data-ttu-id="ed800-263">Sub-redes</span><span class="sxs-lookup"><span data-stu-id="ed800-263">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-264">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="ed800-264">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="ed800-265">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-265">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-266">5.000</span><span class="sxs-lookup"><span data-stu-id="ed800-266">5,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-267">2,000</span><span class="sxs-lookup"><span data-stu-id="ed800-267">2,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-268">175</span><span class="sxs-lookup"><span data-stu-id="ed800-268">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-269">1.400</span><span class="sxs-lookup"><span data-stu-id="ed800-269">1,400</span></span></p></td>
    <td><p><span data-ttu-id="ed800-270">700</span><span class="sxs-lookup"><span data-stu-id="ed800-270">700</span></span></p></td>
    <td><p><span data-ttu-id="ed800-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="ed800-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-272">Reno</span><span class="sxs-lookup"><span data-stu-id="ed800-272">Reno</span></span></p></td>
    <td><p><span data-ttu-id="ed800-273">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-273">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-274">10.000</span><span class="sxs-lookup"><span data-stu-id="ed800-274">10,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-275">4.000</span><span class="sxs-lookup"><span data-stu-id="ed800-275">4,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-276">175</span><span class="sxs-lookup"><span data-stu-id="ed800-276">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-277">2.800</span><span class="sxs-lookup"><span data-stu-id="ed800-277">2,800</span></span></p></td>
    <td><p><span data-ttu-id="ed800-278">700</span><span class="sxs-lookup"><span data-stu-id="ed800-278">700</span></span></p></td>
    <td><p><span data-ttu-id="ed800-279">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="ed800-279">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-280">Portland</span><span class="sxs-lookup"><span data-stu-id="ed800-280">Portland</span></span></p></td>
    <td><p><span data-ttu-id="ed800-281">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-281">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-282">5.000</span><span class="sxs-lookup"><span data-stu-id="ed800-282">5,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-283">4.000</span><span class="sxs-lookup"><span data-stu-id="ed800-283">4,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-284">175</span><span class="sxs-lookup"><span data-stu-id="ed800-284">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-285">2.800</span><span class="sxs-lookup"><span data-stu-id="ed800-285">2,800</span></span></p></td>
    <td><p><span data-ttu-id="ed800-286">700</span><span class="sxs-lookup"><span data-stu-id="ed800-286">700</span></span></p></td>
    <td><p><span data-ttu-id="ed800-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="ed800-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-288">Nova York</span><span class="sxs-lookup"><span data-stu-id="ed800-288">New York</span></span></p></td>
    <td><p><span data-ttu-id="ed800-289">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-289">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-290">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-291">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-292">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-293">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-294">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-294">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="ed800-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-296">Chicago</span><span class="sxs-lookup"><span data-stu-id="ed800-296">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="ed800-297">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-297">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-298">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-299">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-300">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-301">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-302">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-302">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-303">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="ed800-303">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-304">Detroit</span><span class="sxs-lookup"><span data-stu-id="ed800-304">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="ed800-305">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-305">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-306">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-307">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-308">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-309">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-310">(sem limite)</span><span class="sxs-lookup"><span data-stu-id="ed800-310">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="ed800-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="ed800-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="ed800-312">No Lync Server Call Admission Control, as conexões entre as regiões de rede são chamadas de *links de região*.</span><span class="sxs-lookup"><span data-stu-id="ed800-312">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="ed800-313">Para cada link de região, determine o seguinte, da mesma forma que fez para os sites de rede:</span><span class="sxs-lookup"><span data-stu-id="ed800-313">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="ed800-314">Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas.</span><span class="sxs-lookup"><span data-stu-id="ed800-314">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="ed800-315">Se uma nova sessão de áudio fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed800-315">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="ed800-p122">Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed800-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="ed800-318">Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas.</span><span class="sxs-lookup"><span data-stu-id="ed800-318">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="ed800-319">Se uma nova sessão de vídeo fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed800-319">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="ed800-p124">Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed800-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="ed800-322">**Links de região de rede com limites de largura de banda associados**</span><span class="sxs-lookup"><span data-stu-id="ed800-322">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="ed800-323">![Exemplo de limitações entre 3 regiões](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Exemplo de limitações entre 3 regiões")</span><span class="sxs-lookup"><span data-stu-id="ed800-323">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="ed800-324">Informações de largura de banda de link de região (largura de banda em kbps)</span><span class="sxs-lookup"><span data-stu-id="ed800-324">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-325">Nome do link de região</span><span class="sxs-lookup"><span data-stu-id="ed800-325">Region Link Name</span></span></th>
    <th><span data-ttu-id="ed800-326">Primeira região</span><span class="sxs-lookup"><span data-stu-id="ed800-326">First Region</span></span></th>
    <th><span data-ttu-id="ed800-327">Segunda região</span><span class="sxs-lookup"><span data-stu-id="ed800-327">Second Region</span></span></th>
    <th><span data-ttu-id="ed800-328">Limite de BW</span><span class="sxs-lookup"><span data-stu-id="ed800-328">BW Limit</span></span></th>
    <th><span data-ttu-id="ed800-329">Limite de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-329">Audio Limit</span></span></th>
    <th><span data-ttu-id="ed800-330">Limite de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-330">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="ed800-331">Limite de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-331">Video Limit</span></span></th>
    <th><span data-ttu-id="ed800-332">Limite de sessão de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-332">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-333">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="ed800-333">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="ed800-334">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-334">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-335">EMEA</span><span class="sxs-lookup"><span data-stu-id="ed800-335">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="ed800-336">50.000</span><span class="sxs-lookup"><span data-stu-id="ed800-336">50,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-337">20,000</span><span class="sxs-lookup"><span data-stu-id="ed800-337">20,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-338">175</span><span class="sxs-lookup"><span data-stu-id="ed800-338">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-339">14.000</span><span class="sxs-lookup"><span data-stu-id="ed800-339">14,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-340">700</span><span class="sxs-lookup"><span data-stu-id="ed800-340">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-341">EMEA-O LINK</span><span class="sxs-lookup"><span data-stu-id="ed800-341">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="ed800-342">EMEA</span><span class="sxs-lookup"><span data-stu-id="ed800-342">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="ed800-343">APAC</span><span class="sxs-lookup"><span data-stu-id="ed800-343">APAC</span></span></p></td>
    <td><p><span data-ttu-id="ed800-344">25.000</span><span class="sxs-lookup"><span data-stu-id="ed800-344">25,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-345">10.000</span><span class="sxs-lookup"><span data-stu-id="ed800-345">10,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-346">175</span><span class="sxs-lookup"><span data-stu-id="ed800-346">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-347">7.000</span><span class="sxs-lookup"><span data-stu-id="ed800-347">7,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-348">700</span><span class="sxs-lookup"><span data-stu-id="ed800-348">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="ed800-349">Defina uma rota entre cada par de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="ed800-349">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ed800-350">Dois links são necessários para a rota entre as regiões América do Norte e APAC, pois não há um link de região que as conecte diretamente.</span><span class="sxs-lookup"><span data-stu-id="ed800-350">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="ed800-351">Rotas de região</span><span class="sxs-lookup"><span data-stu-id="ed800-351">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-352">Nome da rota de região</span><span class="sxs-lookup"><span data-stu-id="ed800-352">Region Route Name</span></span></th>
    <th><span data-ttu-id="ed800-353">Primeira região</span><span class="sxs-lookup"><span data-stu-id="ed800-353">First Region</span></span></th>
    <th><span data-ttu-id="ed800-354">Segunda região</span><span class="sxs-lookup"><span data-stu-id="ed800-354">Second Region</span></span></th>
    <th><span data-ttu-id="ed800-355">Links de região</span><span class="sxs-lookup"><span data-stu-id="ed800-355">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-356">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="ed800-356">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="ed800-357">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-357">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-358">EMEA</span><span class="sxs-lookup"><span data-stu-id="ed800-358">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="ed800-359">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="ed800-359">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ed800-360">EMEA-DIREÇÃO DA ROTA</span><span class="sxs-lookup"><span data-stu-id="ed800-360">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="ed800-361">EMEA</span><span class="sxs-lookup"><span data-stu-id="ed800-361">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="ed800-362">APAC</span><span class="sxs-lookup"><span data-stu-id="ed800-362">APAC</span></span></p></td>
    <td><p><span data-ttu-id="ed800-363">EMEA-O LINK</span><span class="sxs-lookup"><span data-stu-id="ed800-363">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-364">NA-CHEROKEE-ROUTE</span><span class="sxs-lookup"><span data-stu-id="ed800-364">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="ed800-365">América do Norte</span><span class="sxs-lookup"><span data-stu-id="ed800-365">North America</span></span></p></td>
    <td><p><span data-ttu-id="ed800-366">APAC</span><span class="sxs-lookup"><span data-stu-id="ed800-366">APAC</span></span></p></td>
    <td><p><span data-ttu-id="ed800-367">LINK-NA-EMEA, LINK-EMEA-APAC</span><span class="sxs-lookup"><span data-stu-id="ed800-367">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="ed800-368">Para cada par de sites de rede conectados diretamente por um único link (chamado de link *entre sites*), determine o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ed800-368">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="ed800-369">Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas.</span><span class="sxs-lookup"><span data-stu-id="ed800-369">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="ed800-370">Se uma nova sessão de áudio fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed800-370">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="ed800-p126">Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed800-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="ed800-373">Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas.</span><span class="sxs-lookup"><span data-stu-id="ed800-373">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="ed800-374">Se uma nova sessão de vídeo fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed800-374">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="ed800-p128">Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="ed800-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="ed800-377">**Região da rede CAC América do Norte mostrando as capacidades de largura de banda e limites de largura de banda para o link entre sites entre Reno e Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="ed800-377">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="ed800-378">![Sites de rede restritos por exemplo de largura de banda de WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Sites de rede restritos por exemplo de largura de banda de WAN")</span><span class="sxs-lookup"><span data-stu-id="ed800-378">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="ed800-379">Informações de largura de banda para link entre sites entre dois sites de rede (largura de banda em kbps)</span><span class="sxs-lookup"><span data-stu-id="ed800-379">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ed800-380">Nome do link entre sites</span><span class="sxs-lookup"><span data-stu-id="ed800-380">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="ed800-381">Primeiro site</span><span class="sxs-lookup"><span data-stu-id="ed800-381">First Site</span></span></th>
    <th><span data-ttu-id="ed800-382">Segundo site</span><span class="sxs-lookup"><span data-stu-id="ed800-382">Second Site</span></span></th>
    <th><span data-ttu-id="ed800-383">Limite de BW</span><span class="sxs-lookup"><span data-stu-id="ed800-383">BW Limit</span></span></th>
    <th><span data-ttu-id="ed800-384">Limite de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-384">Audio Limit</span></span></th>
    <th><span data-ttu-id="ed800-385">Limite de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="ed800-385">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="ed800-386">Limite de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-386">Video Limit</span></span></th>
    <th><span data-ttu-id="ed800-387">Limite de sessão de vídeo</span><span class="sxs-lookup"><span data-stu-id="ed800-387">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ed800-388">Reno-Albu-entre sites-link</span><span class="sxs-lookup"><span data-stu-id="ed800-388">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="ed800-389">Reno</span><span class="sxs-lookup"><span data-stu-id="ed800-389">Reno</span></span></p></td>
    <td><p><span data-ttu-id="ed800-390">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="ed800-390">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="ed800-391">20,000</span><span class="sxs-lookup"><span data-stu-id="ed800-391">20,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-392">12.000</span><span class="sxs-lookup"><span data-stu-id="ed800-392">12,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-393">175</span><span class="sxs-lookup"><span data-stu-id="ed800-393">175</span></span></p></td>
    <td><p><span data-ttu-id="ed800-394">5.000</span><span class="sxs-lookup"><span data-stu-id="ed800-394">5,000</span></span></p></td>
    <td><p><span data-ttu-id="ed800-395">700</span><span class="sxs-lookup"><span data-stu-id="ed800-395">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="ed800-396">Próximas Etapas</span><span class="sxs-lookup"><span data-stu-id="ed800-396">Next Steps</span></span>

<span data-ttu-id="ed800-397">Depois de coletar as informações necessárias, você pode executar a implantação do CAC usando o Shell de gerenciamento do Lync Server ou o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed800-397">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ed800-398">Embora seja possível executar a maioria das tarefas de configuração de rede usando o painel de controle do Lync Server, para criar sub-redes e links entre sites, você deve usar o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed800-398">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="ed800-399">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o cmdlet <STRONG>New-CsNetworkSubnet</STRONG> e o cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ed800-399">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

