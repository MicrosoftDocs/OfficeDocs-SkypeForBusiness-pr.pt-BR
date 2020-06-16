---
title: Lync Server 2013; Criar rotas entre regiões de rede
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 156f2322d5b1b7cc1951f1cbd4df41eb231a8170
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="45eff-102">Criar rotas entre regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45eff-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45eff-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="45eff-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="45eff-104">A *network interregion route* defines the route between a pair of network regions.</span><span class="sxs-lookup"><span data-stu-id="45eff-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="45eff-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span><span class="sxs-lookup"><span data-stu-id="45eff-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="45eff-106">This enables every network region within the deployment to access every other region.</span><span class="sxs-lookup"><span data-stu-id="45eff-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="45eff-107">Enquanto os vínculos de região definem limitações de largura de banda nas conexões entre regiões, uma rota entre regiões de rede determina o caminho vinculado que a conexão percorrerá de uma região à outra.</span><span class="sxs-lookup"><span data-stu-id="45eff-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="45eff-108">Para obter detalhes sobre como trabalhar com rotas entre regiões de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="45eff-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="45eff-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="45eff-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="45eff-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="45eff-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="45eff-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="45eff-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="45eff-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="45eff-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="45eff-113">Na topologia de exemplo, as rotas entre regiões de rede devem ser definidas para cada um dos três pares de regiões: América do Norte/EMEA, EMEA/APAC e América do Norte/APAC.</span><span class="sxs-lookup"><span data-stu-id="45eff-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="45eff-114">Para criar rotas entre regiões de rede usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="45eff-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="45eff-115">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="45eff-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45eff-116">Execute o cmdlet **New-CsNetworkInterRegionRoute** para definir as rotas necessárias.</span><span class="sxs-lookup"><span data-stu-id="45eff-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="45eff-117">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="45eff-117">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="45eff-118">A rota entre regiões de rede América do Norte/APAC requer dois links de regiões de rede porque não há um link de região de rede direta entre elas.</span><span class="sxs-lookup"><span data-stu-id="45eff-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="45eff-119">Para criar rotas entre regiões de rede usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="45eff-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="45eff-120">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="45eff-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="45eff-121">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="45eff-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="45eff-122">Na barra de navegação esquerda, clique em **Configuração de Rede**.</span><span class="sxs-lookup"><span data-stu-id="45eff-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="45eff-123">Clique no botão de navegações **Rota de Região**.</span><span class="sxs-lookup"><span data-stu-id="45eff-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="45eff-124">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="45eff-124">Click **New**.</span></span>

5.  <span data-ttu-id="45eff-125">Na página **Nova Rota de Região**, clique em **Nome** e digite um nome para a rota entre regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="45eff-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="45eff-126">Clique em **região de rede \# 1**e, em seguida, clique em uma região de rede na lista que você deseja rotear para a região de rede \# 2.</span><span class="sxs-lookup"><span data-stu-id="45eff-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="45eff-127">Clique em **região de rede \# 2**e, em seguida, clique em uma região de rede na lista que você deseja rotear para a região de rede \# 1.</span><span class="sxs-lookup"><span data-stu-id="45eff-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="45eff-128">Clique em **Adicionar** próximo ao campo **Links de Região de Rede**  e adicione um link de região de rede que será usado na rota entre regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="45eff-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="45eff-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span><span class="sxs-lookup"><span data-stu-id="45eff-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="45eff-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span><span class="sxs-lookup"><span data-stu-id="45eff-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="45eff-131">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="45eff-131">Click **Commit**.</span></span>

10. <span data-ttu-id="45eff-132">Para concluir a criação de rotas entre regiões de rede para sua topologia de rede, repita as etapas 4 a 9 com configurações de outras rotas entre regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="45eff-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

