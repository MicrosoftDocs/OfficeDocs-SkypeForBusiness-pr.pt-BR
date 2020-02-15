---
title: 'Lync Server 2013: configurações de rede para os recursos avançados do Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d6b01009aac5fdaf3d69e24b4137897e70051b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="4e909-102">Configurações de rede para os recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e909-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e909-103">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="4e909-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="4e909-104">O Lync Server tem três recursos avançados do Enterprise Voice: controle de admissão de chamadas (CAC), serviços de emergência (E9-1-1) e bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="4e909-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="4e909-105">Esses recursos compartilham determinados requisitos de configuração para regiões de rede, sites de rede e Associação de cada sub-rede na topologia do Lync Server com um site de rede.</span><span class="sxs-lookup"><span data-stu-id="4e909-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="4e909-106">Para obter detalhes sobre o planejamento da implantação desses recursos, consulte:</span><span class="sxs-lookup"><span data-stu-id="4e909-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="4e909-107">Planejando o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e909-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="4e909-108">Planejamento de serviços de emergência (E9-1-1) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e909-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="4e909-109">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e909-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="4e909-110">Para obter detalhes sobre a implantação de cada um desses recursos, consulte [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="4e909-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4e909-111">Este tópico fornece uma visão geral dos requisitos de configuração que são comuns a todos os três recursos avançados do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4e909-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="4e909-112">Regiões de Rede</span><span class="sxs-lookup"><span data-stu-id="4e909-112">Network Regions</span></span>

<span data-ttu-id="4e909-113">Uma região de rede é um hub de rede ou backbone de rede usada somente na configuração do serviço de controle de admissão de chamadas (CAC),  E9-1-1 e bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="4e909-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e909-114">As regiões de rede não são as mesmas que as regiões de conferência discada do Lync Server, que são necessárias para associar os números de acesso de conferência discada a um ou mais planos de discagem do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="4e909-115">Para obter detalhes sobre as regiões de conferência discada, consulte <A href="lync-server-2013-dial-in-conferencing-requirements.md">requisitos de conferência discada no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4e909-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="4e909-116">O CAC requer que todas as regiões de rede tenham um site central do Lync Server associado, que gerencia o tráfego de mídia dentro da região (ou seja, ele toma decisões com base nas políticas que você configurou, em relação a se ou não uma sessão de áudio ou vídeo em tempo real pode ser estabelecida).</span><span class="sxs-lookup"><span data-stu-id="4e909-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="4e909-117">Os sites centrais do Lync Server não representam locais geográficos, mas sim grupos lógicos de servidores configurados como um pool ou um conjunto de pools.</span><span class="sxs-lookup"><span data-stu-id="4e909-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="4e909-118">Para obter detalhes sobre sites centrais, consulte [Reference topologias in Lync Server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4e909-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="4e909-119">Confira também as [topologias com suporte no Lync Server 2013](lync-server-2013-supported-topologies.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="4e909-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="4e909-120">Para configurar uma região de rede, você pode usar a guia **regiões** na seção **configuração de rede** do painel de controle do Lync Server ou executar os cmdlets do Shell de gerenciamento do Lync Server **New-CsNetworkRegion** ou **set-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="4e909-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="4e909-121">Para obter instruções, consulte [criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="4e909-122">As mesmas definições de região de rede são compartilhadas por todos os três recursos avançados do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4e909-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="4e909-123">Se você já criou áreas de rede para um recurso, não será necessário criar novas regiões de rede para outros recursos.</span><span class="sxs-lookup"><span data-stu-id="4e909-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="4e909-124">No entanto, pode ser necessário modificar uma definição de região de rede existente para aplicar as configurações específicas do recurso.</span><span class="sxs-lookup"><span data-stu-id="4e909-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="4e909-125">Por exemplo, se você criou áreas de rede para E9-1-1 (que não requer um site central associado) e posteriormente implantou o serviço de controle de admissão de chamadas, é necessário modificar cada uma das definições de região de rede para especificar um site central.</span><span class="sxs-lookup"><span data-stu-id="4e909-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="4e909-126">Para associar um site central do Lync Server a uma região de rede, você especifica o nome do site central, seja usando a seção **configuração de rede** do painel de controle do Lync Server ou executando os cmdlets do Shell de gerenciamento do Lync Server **New-CsNetworkRegion** ou **set-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="4e909-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="4e909-127">Para obter instruções, consulte [criar ou modificar uma região de rede no Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="4e909-128">Sites de Rede</span><span class="sxs-lookup"><span data-stu-id="4e909-128">Network Sites</span></span>

<span data-ttu-id="4e909-p107">Um site de rede representa uma localização geográfica, como um escritório principal, filiais ou regionais. Cada site de rede deve ser associado a uma região específica de rede.</span><span class="sxs-lookup"><span data-stu-id="4e909-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e909-131">Os sites de rede são usados apenas pelos recursos avançados do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4e909-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="4e909-132">Eles não são os mesmos que os sites de filial que você configura em sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="4e909-133">Para obter detalhes sobre sites de filial, consulte <A href="lync-server-2013-reference-topologies.md">Reference topologias in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4e909-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="4e909-134">Confira também as <A href="lync-server-2013-supported-topologies.md">topologias com suporte no Lync Server 2013</A> na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="4e909-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="4e909-135">Para configurar um site de rede e associá-lo a uma região de rede, você pode usar a seção **configuração de rede** do painel de controle do Lync Server ou executar os cmdlets **New-CsNetworkSite** ou **set-CsNetworkSite** do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="4e909-136">Para obter detalhes, consulte [create or Modify a Network site in Lync server 2013](lync-server-2013-create-or-modify-a-network-site.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="4e909-137">Identificar Subredes IP</span><span class="sxs-lookup"><span data-stu-id="4e909-137">Identify IP Subnets</span></span>

<span data-ttu-id="4e909-p110">Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas a cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.</span><span class="sxs-lookup"><span data-stu-id="4e909-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="4e909-p111">No exemplo, o site de Nova York na região da América do Norte pode ser atribuído às seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suponha que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, seu computador terá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="4e909-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4e909-142">As subredes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="4e909-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="4e909-143">Um cliente do Lync usa seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada.</span><span class="sxs-lookup"><span data-stu-id="4e909-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="4e909-144">Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comprar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="4e909-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="4e909-145">Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais.</span><span class="sxs-lookup"><span data-stu-id="4e909-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="4e909-146">(Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará mesmo se você configurar as subredes virtuais.)</span><span class="sxs-lookup"><span data-stu-id="4e909-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="4e909-147">Por exemplo, se um cliente do Lync entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede IP 255.255.255.0, ele solicitará a ID de bypass associada à sub-rede 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="4e909-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="4e909-148">Se a subrede é definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="4e909-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="4e909-149">Portanto, é importante que o administrador insira as subredes exatamente conforme fornecido pelos clientes do Lync (que são provisionados com sub-redes durante a configuração da rede, seja estático ou pelo protocolo DHCP (Dynamic Host Configuration Protocol).)</span><span class="sxs-lookup"><span data-stu-id="4e909-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="4e909-150">Associando Subredes aos Locais de Rede</span><span class="sxs-lookup"><span data-stu-id="4e909-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="4e909-151">Cada subrede na rede corporativa deve ser associado um site de rede (ou seja, cada sub-rede deve ser associado a uma localização geográfica).</span><span class="sxs-lookup"><span data-stu-id="4e909-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="4e909-152">Essa associação de sub-redes permite que os recursos avançados do Enterprise Voice localizem geograficamente os pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4e909-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="4e909-153">Por exemplo, localizar os pontos de extremidade permite que CAC regule o fluxo de áudio e dados de vídeo em tempo real indo e voltando do local de rede.</span><span class="sxs-lookup"><span data-stu-id="4e909-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="4e909-154">Para associar sub-redes a sites de rede, você pode usar a seção **configuração de rede** do painel de controle do Lync Server ou pode usar o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="4e909-155">Para obter instruções, consulte [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e909-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e909-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e909-156">See Also</span></span>


[<span data-ttu-id="4e909-157">Planejando o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e909-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="4e909-158">Planejamento de serviços de emergência (E9-1-1) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e909-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="4e909-159">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e909-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

