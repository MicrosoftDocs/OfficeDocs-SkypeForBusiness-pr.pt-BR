---
title: 'Lync Server 2013: Habilitando o bypass de mídia de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4caab36c57c3c8901bd0691e5623f232879bd03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528518"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="48975-102">Habilitando o bypass de mídia de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48975-102">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48975-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="48975-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="48975-104">As configurações de bypass de mídia são aplicadas globalmente em uma implantação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48975-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="48975-105">O desvio de mídia permite que chamadas ignorem o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="48975-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="48975-106">Para obter detalhes sobre quando usar o bypass de mídia, consulte [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na seção Planning.</span><span class="sxs-lookup"><span data-stu-id="48975-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="48975-107">Você pode habilitar e configurar o bypass de mídia no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48975-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="48975-108">Para habilitar e configurar o desvio de mídia</span><span class="sxs-lookup"><span data-stu-id="48975-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="48975-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="48975-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="48975-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48975-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="48975-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="48975-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="48975-112">Na barra de navegação à esquerda, clique em **Configuração da Rede** e clique em **Global**.</span><span class="sxs-lookup"><span data-stu-id="48975-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="48975-p103">Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.</span><span class="sxs-lookup"><span data-stu-id="48975-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="48975-115">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="48975-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="48975-116">Na página **Editar Configuração Global**, clique na opção **Habilitar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="48975-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="48975-117">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="48975-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="48975-118">**Sempre ignorar**     Selecione essa opção para tentar o bypass de mídia em todas as chamadas.</span><span class="sxs-lookup"><span data-stu-id="48975-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="48975-119">Esta opção estará indisponível se o controle de admissão de chamadas (CAC) estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="48975-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="48975-120">Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="48975-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="48975-121">Não existe a necessidade de controle de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="48975-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="48975-122">Não existe a necessidade de uma configuração refinada para determinar quando o desvio deve acontecer.</span><span class="sxs-lookup"><span data-stu-id="48975-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="48975-123">Existe conectividade total entre gateways e clientes.</span><span class="sxs-lookup"><span data-stu-id="48975-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="48975-124">**Usar configuração**     de sites e regiões Se o CAC estiver habilitado, essa opção é selecionada por padrão e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="48975-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="48975-125">Quando esta opção está selecionada, a configuração de rede de sites e regiões será usada para determinar quando o desvio de mídia será possível.</span><span class="sxs-lookup"><span data-stu-id="48975-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="48975-126">Se esta opção for selecionada, você pode optar por habilitar o desvio para sites que não estão mapeados.</span><span class="sxs-lookup"><span data-stu-id="48975-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="48975-127">Clique na opção **Habilitar desvio para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região, que não possuem restrições de largura de banda (por exemplo, um site central grande) e se tiver também alguns sites de filial associados à mesma região que executa as restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="48975-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="48975-128">Ao habilitar o desvio para sites não mapeados, a configuração é eficiente porque somente as sub-redes associadas aos sites de filial são especificadas, em vez da necessidade de especificas todas as sub-redes associadas as todos os sites.</span><span class="sxs-lookup"><span data-stu-id="48975-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="48975-129">É recomendável não selecionar a opção **Habilitar desvio para sites não mapeados** se o CAC estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="48975-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="48975-130">Clique em **Confirmar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="48975-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48975-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="48975-131">See Also</span></span>


[<span data-ttu-id="48975-132">Desabilitando o bypass de mídia de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48975-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="48975-133">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48975-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="48975-134">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48975-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

