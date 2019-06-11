---
title: 'Lync Server 2013: Habilitando o bypass de mídia de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff18c69d6d257a520d2413bff266c97879d4963e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="511b7-102">Habilitando o bypass de mídia de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="511b7-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="511b7-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="511b7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="511b7-104">As configurações de bypass de mídia se aplicam globalmente em uma implantação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="511b7-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="511b7-105">O bypass de mídia permite que as chamadas ignorem o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="511b7-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="511b7-106">Para obter detalhes sobre quando usar o bypass de mídia, consulte [planejando a bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na seção planejamento.</span><span class="sxs-lookup"><span data-stu-id="511b7-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="511b7-107">Você pode habilitar e configurar o bypass de mídia no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="511b7-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="511b7-108">Para habilitar e configurar o bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="511b7-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="511b7-109">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="511b7-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="511b7-110">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="511b7-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="511b7-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="511b7-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="511b7-112">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **global**.</span><span class="sxs-lookup"><span data-stu-id="511b7-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="511b7-113">Na página **global** , clique em configuração **global** .</span><span class="sxs-lookup"><span data-stu-id="511b7-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="511b7-114">Sempre existe apenas uma configuração, e ela é sempre chamada de global.</span><span class="sxs-lookup"><span data-stu-id="511b7-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="511b7-115">No menu **Editar** , clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="511b7-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="511b7-116">Na página **Editar configuração global** , clique na caixa de seleção **habilitar bypass de mídia** .</span><span class="sxs-lookup"><span data-stu-id="511b7-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="511b7-117">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="511b7-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="511b7-118">**Sempre ignorar**   Selecione esta opção para tentar ignorar a mídia em todas as chamadas.</span><span class="sxs-lookup"><span data-stu-id="511b7-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="511b7-119">Essa opção não estará disponível se o controle de admissão de chamadas (CAC) estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="511b7-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="511b7-120">Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="511b7-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="511b7-121">Não há necessidade de controle de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="511b7-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="511b7-122">Não é preciso ter uma configuração refinada para determinar quando bypass deve acontecer.</span><span class="sxs-lookup"><span data-stu-id="511b7-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="511b7-123">Há conectividade total entre gateways e clientes.</span><span class="sxs-lookup"><span data-stu-id="511b7-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="511b7-124">**Usar a configuração**   de sites e regiões se o CAC estiver habilitado, essa opção será selecionada por padrão e não poderá ser alterada.</span><span class="sxs-lookup"><span data-stu-id="511b7-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="511b7-125">Quando essa opção estiver selecionada, os sites de configuração de rede e regiões serão usados para determinar quando o bypass de mídia é possível.</span><span class="sxs-lookup"><span data-stu-id="511b7-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="511b7-126">Se você selecionar essa opção, poderá optar por habilitar o bypass para sites que não estão mapeados.</span><span class="sxs-lookup"><span data-stu-id="511b7-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="511b7-127">Marque a caixa de seleção **Permitir bypass para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região que não têm restrições de largura de banda (por exemplo, um site central grande) e também tem alguns sites de filiais associados ao mesma região que tem restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="511b7-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="511b7-128">Quando você habilita o bypass para sites não mapeados, a configuração é simplificada porque você especifica somente as sub-redes associadas a sites de ramificação, em vez de precisar especificar todas as sub-redes associadas a todos os sites.</span><span class="sxs-lookup"><span data-stu-id="511b7-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="511b7-129">Recomendamos que você não marque a caixa de seleção **Permitir bypass para sites não mapeados** se o CAC estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="511b7-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="511b7-130">Clique em **confirmar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="511b7-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="511b7-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="511b7-131">See Also</span></span>


[<span data-ttu-id="511b7-132">Desativando o bypass de mídia de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="511b7-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="511b7-133">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="511b7-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="511b7-134">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="511b7-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

