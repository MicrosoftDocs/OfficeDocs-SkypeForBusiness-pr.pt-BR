---
title: Definir as configurações globais de bypass de mídia para usar informações locais e da região
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="46c75-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="46c75-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c75-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="46c75-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="46c75-104">Este tópico pressupõe que você já configurou a bypass de mídia para todas as conexões de tronco do servidor de mediação para um par (um gateway PSTN (rede telefônica pública comutada), um PBX IP ou um controlador de borda de sessão (SBC) em um serviço de telefonia pela Internet Provedor (ITSP) para um site ou serviço específico para o qual você deseja que a mídia ignore o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="46c75-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="46c75-105">Este tópico também pressupõe que você definiu todos os sites centrais e sites de ramificação no construtor de topologias de uma maneira que corresponde à região de rede, ao site de rede e à configuração de sub-rede que você executou de acordo com as etapas em <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no lync Server 2013</A>e <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="46c75-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="46c75-106">Se eles não corresponderem, o bypass do Media não será bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="46c75-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="46c75-107">Além de habilitar a bypass de mídia para conexões de tronco individuais associadas a um par, você também deve definir configurações globais.</span><span class="sxs-lookup"><span data-stu-id="46c75-107">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="46c75-108">Se você usar as etapas deste tópico para definir configurações globais para bypass de mídia, pressupõe-se que uma ou ambas as situações a seguir afetem sua configuração:</span><span class="sxs-lookup"><span data-stu-id="46c75-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="46c75-109">Você *não* tem uma boa conectividade entre os pontos de extremidade do Lync Server e os pares para os quais configurou a mídia ignorada na conexão do tronco.</span><span class="sxs-lookup"><span data-stu-id="46c75-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="46c75-110">O controle de admissão de chamadas (CAC) para gerenciamento de largura de banda está habilitado.</span><span class="sxs-lookup"><span data-stu-id="46c75-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="46c75-111">Para obter detalhes sobre as considerações para o controle de admissão de chamadas e o bypass de mídia, consulte a seção "controle de admissão de chamadas de conexão PSTN" em <A href="lync-server-2013-media-bypass-and-mediation-server.md">ignorar mídias e servidor de mediação no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="46c75-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="46c75-p103">As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o bypass de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do bypass de chamada.</span><span class="sxs-lookup"><span data-stu-id="46c75-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="46c75-115">Ou siga estas etapas se quiser usar as informações de site e região para tomar a decisão de ignorar, mas não tiver intenção de habilitar o controle de admissão de chamadas.</span><span class="sxs-lookup"><span data-stu-id="46c75-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="46c75-116">Nesse caso, os links restritos de largura de banda ainda precisarão ser representados pelas políticas entre sites de rede, conforme descrito em [criar políticas entre sites de rede no Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="46c75-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="46c75-117">As restrições de largura de banda reais não são tão importantes nesse caso porque o controle de admissão de chamadas não foi habilitado.</span><span class="sxs-lookup"><span data-stu-id="46c75-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="46c75-118">Em vez disso, esses links são usados para sub-redes de partição para especificar aqueles que não têm limites de largura de banda e podem, portanto, empregar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="46c75-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="46c75-119">Observe que isso também é verdadeiro quando o controle de admissão de chamadas e o bypass de mídia estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="46c75-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="46c75-120">Além disso, para bypass funcionar corretamente, deve haver consistência entre um site conforme definido no construtor de topologias e conforme é definido quando você configura regiões de rede e sites de rede.</span><span class="sxs-lookup"><span data-stu-id="46c75-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="46c75-121">Por exemplo, se você tiver um site de ramificação que você definiu no construtor de topologias como tendo apenas um gateway PSTN implantado, esse site de filial deve ser configurado com uma política de voz empresarial que permita que os usuários do site de filial tenham suas chamadas PSTN roteadas por meio da PSTN Gateway no site da filial.</span><span class="sxs-lookup"><span data-stu-id="46c75-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="46c75-122">Para configurar informações de site e de região para bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="46c75-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="46c75-123">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46c75-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="46c75-124">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46c75-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="46c75-125">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="46c75-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="46c75-126">Dê dois cliques na configuração **Global** na tabela.</span><span class="sxs-lookup"><span data-stu-id="46c75-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="46c75-127">Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar bypass de mídia**.</span><span class="sxs-lookup"><span data-stu-id="46c75-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="46c75-128">Clique em **Usar as configurações de sites e região**.</span><span class="sxs-lookup"><span data-stu-id="46c75-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="46c75-129">Se necessário, marque a caixa de seleção **Habilitar bypass de mídia para sites não mapeados**.</span><span class="sxs-lookup"><span data-stu-id="46c75-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="46c75-p107">Marque essa caixa de seleção somente se você tiver um ou mais sites grandes associados na mesma região e que não possuem restrições de largura de banda (por exemplo, um grande site central), mas também tem sites de filial associados à mesma região e que possuem restrições de largura de banda. Ao habilitar o bypass para sites não mapeados, a configuração é simplificada de forma que você especifica apenas as sub-redes associadas com os sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque essa caixa de seleção se o controle de admissão de chamadas estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="46c75-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="46c75-133">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="46c75-133">Click **Commit**.</span></span>

<span data-ttu-id="46c75-134">Em seguida, adicione sub-redes ao site de rede, conforme descrito em [associar sub-redes a sites de rede para ignorar mídia no Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="46c75-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="46c75-135">(Os procedimentos reais para associar sub-redes com sites de rede estão descritos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) Após associar todas as sub-redes com sites de rede, a implantação de bypass de mídia é concluída.</span><span class="sxs-lookup"><span data-stu-id="46c75-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="46c75-136">Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="46c75-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="46c75-137">Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="46c75-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46c75-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="46c75-138">See Also</span></span>


[<span data-ttu-id="46c75-139">Associar sub-redes a sites de rede para ignorar mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c75-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

