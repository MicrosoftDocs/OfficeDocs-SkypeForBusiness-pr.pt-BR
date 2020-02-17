---
title: 'Lync Server 2013: exibindo informações de rota de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6acf4fbc1766adbe2c2a14a28cfbeef16f199b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="4821d-102">Exibindo informações de rota de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4821d-102">Viewing network region route information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4821d-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4821d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4821d-104">Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="4821d-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="4821d-105">Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra.</span><span class="sxs-lookup"><span data-stu-id="4821d-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="4821d-106">Use os procedimentos a seguir para exibir as rotas de região de rede existentes no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4821d-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="4821d-107">Para obter detalhes sobre como criar ou modificar as rotas de região de rede, consulte [criando ou modificando rotas de região de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="4821d-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="4821d-108">Para exibir informações de rota de região de rede no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="4821d-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4821d-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="4821d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4821d-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4821d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4821d-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4821d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4821d-112">Na barra de navegação esquerda, clique em **Configuração da Rede** e clique em **Rota de Região**.</span><span class="sxs-lookup"><span data-stu-id="4821d-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="4821d-113">Na página **Rota de Região**, clique na rota de região que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="4821d-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4821d-114">É possível ver apenas uma rota de região por vez.</span><span class="sxs-lookup"><span data-stu-id="4821d-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="4821d-115">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="4821d-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4821d-116">Exibindo informações de rota de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4821d-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4821d-117">As informações de rota de região de rede podem ser visualizadas usando o Windows PowerShell e o cmdlet Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="4821d-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="4821d-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4821d-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4821d-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="4821d-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="4821d-120">Para exibir informações de rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="4821d-120">To view network region route information</span></span>

  - <span data-ttu-id="4821d-121">Para exibir informações sobre todas as suas rotas de região de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="4821d-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="4821d-122">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="4821d-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="4821d-123">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="4821d-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4821d-124">Confira Também</span><span class="sxs-lookup"><span data-stu-id="4821d-124">See Also</span></span>


[<span data-ttu-id="4821d-125">Criando ou modificando rotas de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4821d-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="4821d-126">Excluindo rotas de região de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4821d-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

