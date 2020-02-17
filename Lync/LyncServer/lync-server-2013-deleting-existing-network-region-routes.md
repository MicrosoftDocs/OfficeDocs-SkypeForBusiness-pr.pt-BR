---
title: 'Lync Server 2013: excluindo rotas de região de rede existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 030980ca18e21915f514435a8682ec8ddcf78286
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="559ee-102">Excluindo rotas de região de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="559ee-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="559ee-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="559ee-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="559ee-104">Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="559ee-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="559ee-105">Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra.</span><span class="sxs-lookup"><span data-stu-id="559ee-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="559ee-106">Você pode usar o painel de controle do Lync Server para configurar rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="559ee-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="559ee-107">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="559ee-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="559ee-108">Use este tópico para excluir rotas de região de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="559ee-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="559ee-109">Para obter detalhes sobre como criar ou modificar as rotas de região de rede, consulte [criando ou modificando rotas de região de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="559ee-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="559ee-110">Para excluir uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="559ee-110">To delete a network region route</span></span>

1.  <span data-ttu-id="559ee-111">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="559ee-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="559ee-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="559ee-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="559ee-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="559ee-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="559ee-114">Na barra de navegação esquerda, clique em **Configuração de Rede** e depois em **Rota de Região**.</span><span class="sxs-lookup"><span data-stu-id="559ee-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="559ee-115">Na página **Rota de Região**, clique na rota de região que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="559ee-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="559ee-p103">Você pode excluir mais de uma rota de região por vez. Para fazer isso, pressione CTRL e selecione várias rotas de região mantendo pressionada a tecla CTRL. Para selecionar todas as rotas da região, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="559ee-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="559ee-119">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="559ee-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="559ee-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="559ee-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="559ee-121">Confira Também</span><span class="sxs-lookup"><span data-stu-id="559ee-121">See Also</span></span>


[<span data-ttu-id="559ee-122">Criando ou modificando rotas de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="559ee-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="559ee-123">[Configurar uma Rota de Região de Rede](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="559ee-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="559ee-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="559ee-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="559ee-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="559ee-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="559ee-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="559ee-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="559ee-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="559ee-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

