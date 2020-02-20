---
title: Definir as configurações globais de bypass de mídia para usar informações do site e da região
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4104a8892fd613b788862cf8a90db5fbef6c9f85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="6227b-102">Definir as configurações globais de bypass de mídia no Lync Server 2013 para usar informações do site e da região</span><span class="sxs-lookup"><span data-stu-id="6227b-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6227b-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6227b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6227b-104">Este tópico considera que você já tenha configurado o desvio de mídia em todas as conexões de tronco do Servidor de Mediação para um ponto (gateway PSTN, PBX IP ou Controlador de Limite de Sessões no Provedor de Serviços de Telefonia pela Internet) de um site ou serviço específico no qual deseja que a mídia ignore o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="6227b-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="6227b-105">Este tópico também pressupõe que você tenha definido todos os sites centrais e sites de filial no construtor de topologias de uma maneira que corresponda à região de rede, ao site de rede e à configuração de sub-rede que você executou de acordo com as etapas em <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync 2013 2013 Server</A> <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md"></A></span><span class="sxs-lookup"><span data-stu-id="6227b-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="6227b-106">Se elas não forem compatíveis, o desvio de mídia não será bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="6227b-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="6227b-p102">Além de habilitar o desvio de mídia para conexões de tronco individuais associadas a um par, você também precisa definir as configurações globais. Se você usar as etapas deste tópico para definir as configurações globais do desvio de mídia, a hipótese é de que uma ou ambas as situações a seguir afetem sua configuração:</span><span class="sxs-lookup"><span data-stu-id="6227b-p102">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings. If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="6227b-109">Você *não* tem uma boa conectividade entre os pontos de extremidade do Lync Server e os pontos para os quais você configurou o bypass de mídia na conexão do tronco.</span><span class="sxs-lookup"><span data-stu-id="6227b-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="6227b-110">O controle de admissão de chamadas (CAC) para gerenciamento de largura de banda está habilitado.</span><span class="sxs-lookup"><span data-stu-id="6227b-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6227b-111">Para obter detalhes sobre as considerações para o controle de admissão de chamadas e o bypass de mídia, consulte a seção "controle de admissão de chamadas de conexões PSTN" no <A href="lync-server-2013-media-bypass-and-mediation-server.md">bypass de mídia e no servidor de mediação no Lync server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="6227b-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="6227b-p103">As informações de região de rede e de site de rede são compartilhadas entre os recursos avançados do Enterprise Voice de controle de admissão de chamadas e de desvio de mídia quando os dois estão habilitados. Portanto, se você já configurou o controle de admissão de chamadas, não é preciso usar o procedimento a seguir para editar as informações do site e da região especificamente para o desvio de mídia. Siga as etapas neste procedimento se você ainda não tiver configurado as regiões e os sites de rede quanto ao controle de admissão de chamadas e se quiser alterar as configurações do desvio de chamada.</span><span class="sxs-lookup"><span data-stu-id="6227b-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="6227b-115">Ou siga estas etapas se quiser usar as informações do site e da região para tomar a decisão do desvio de mídia, mas não tem a intenção de habilitar o controle de admissão de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6227b-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="6227b-116">Nesse caso, os links restritos de largura de banda ainda precisam ser representados por meio de políticas entre sites de rede, conforme descrito em [Create Network intersite Policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6227b-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="6227b-117">As restrições atuais de largura de banda não são tão importantes nesse caso porque o controle de admissão de chamada ainda não foi habilitado.</span><span class="sxs-lookup"><span data-stu-id="6227b-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="6227b-118">Em vez disso, esses links são usados para sub-redes de partição para especificar aquelas sem limites de largura de banda e podem empregar desvios de mídia.</span><span class="sxs-lookup"><span data-stu-id="6227b-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="6227b-119">Note que isso também ocorre quando o controle de admissão de chamada e o desvio de mídia estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="6227b-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="6227b-120">Além disso, para que o bypass funcione corretamente, deve haver consistência entre um site conforme definido no construtor de topologias e conforme é definido quando você configura regiões de rede e sites de rede.</span><span class="sxs-lookup"><span data-stu-id="6227b-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="6227b-121">Por exemplo, se você tiver um site de filial que você definiu no construtor de topologias como tendo apenas um gateway PSTN implantado, esse site de filial deverá ser configurado com uma política de Enterprise Voice que permita que os usuários do site de filial tenham suas chamadas PSTN roteadas através da PSTN Gateway no local da filial.</span><span class="sxs-lookup"><span data-stu-id="6227b-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="6227b-122">Para configurar informações de site e de região para desvio de mídia</span><span class="sxs-lookup"><span data-stu-id="6227b-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="6227b-123">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6227b-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6227b-124">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6227b-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="6227b-125">Na barra de navegação à esquerda, clique em **Configurações de rede**.</span><span class="sxs-lookup"><span data-stu-id="6227b-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="6227b-126">Dê dois cliques na configuração **Global** na tabela.</span><span class="sxs-lookup"><span data-stu-id="6227b-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="6227b-127">Na página **Editar Configurações Globais**, marque a caixa de seleção **Habilitar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="6227b-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="6227b-128">Clique em **Usar as configurações de sites e região**.</span><span class="sxs-lookup"><span data-stu-id="6227b-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="6227b-129">Se necessário, marque a caixa de seleção **Habilitar desvio de mídia para sites não mapeados**.</span><span class="sxs-lookup"><span data-stu-id="6227b-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6227b-p107">Marque essa caixa de seleção somente se você tiver um ou mais sites grandes associados na mesma região e que não possuem restrições de largura de banda (por exemplo, um grande site central), mas também tem sites de filial associados à mesma região e que possuem restrições de largura de banda. Ao habilitar o desvio para sites não mapeados, a configuração é simplificada de forma que você especifica apenas as sub-redes associadas com os sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites. Recomendamos que você não marque essa caixa de seleção se o controle de admissão de chamadas estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="6227b-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="6227b-133">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6227b-133">Click **Commit**.</span></span>

<span data-ttu-id="6227b-134">Em seguida, adicione sub-redes ao site de rede, conforme descrito em [associar sub-redes a sites de rede para bypass de mídia no Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="6227b-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="6227b-135">(Os procedimentos reais para associar sub-redes a sites de rede são descritos em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) Após associar todas as sub-redes a sites de rede, a implantação de bypass de mídia estará concluída.</span><span class="sxs-lookup"><span data-stu-id="6227b-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6227b-136">Se ainda não tiverem sido criadas as regiões e os sites de rede, é preciso criá-los antes de prosseguir com a implantação do desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="6227b-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="6227b-137">Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">criar ou modificar uma região de rede no Lync Server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6227b-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6227b-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="6227b-138">See Also</span></span>


[<span data-ttu-id="6227b-139">Associar sub-redes a sites de rede para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6227b-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

