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
ms.openlocfilehash: e9f9ba7c20aff0bba3101edc9b04f3704314cfc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="44b78-102">Excluindo rotas de região de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44b78-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44b78-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="44b78-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="44b78-104">Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="44b78-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="44b78-105">Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra.</span><span class="sxs-lookup"><span data-stu-id="44b78-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="44b78-106">Você pode usar o painel de controle do Lync Server para configurar rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="44b78-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="44b78-107">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="44b78-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="44b78-108">Use este tópico para excluir as rotas de região de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="44b78-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="44b78-109">Para obter detalhes sobre como criar ou modificar as rotas de região de rede, consulte [criando ou modificando rotas de região de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="44b78-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="44b78-110">Para excluir uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="44b78-110">To delete a network region route</span></span>

1.  <span data-ttu-id="44b78-111">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="44b78-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44b78-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44b78-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="44b78-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="44b78-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="44b78-114">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **rota de região**.</span><span class="sxs-lookup"><span data-stu-id="44b78-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="44b78-115">Na página **rota de região** , clique na rota de região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="44b78-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="44b78-116">Você pode excluir mais de uma rota de região por vez.</span><span class="sxs-lookup"><span data-stu-id="44b78-116">You can delete more than one region route at a time.</span></span> <span data-ttu-id="44b78-117">Para fazer isso, pressione CTRL e selecione várias rotas de região enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="44b78-117">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="44b78-118">Ou, para selecionar todas as rotas de região, clique em <STRONG>selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="44b78-118">Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="44b78-119">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="44b78-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="44b78-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="44b78-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44b78-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="44b78-121">See Also</span></span>


[<span data-ttu-id="44b78-122">Criando ou modificando rotas de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44b78-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="44b78-123">[Configurar uma Rota de Região de Rede](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="44b78-123">[Configure a Network Region Route](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="44b78-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="44b78-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="44b78-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="44b78-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="44b78-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="44b78-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="44b78-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="44b78-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

