---
title: Lync Server 2013; Criar rotas interregions de rede
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: be1c28450708660e2322144802c81d5458ded6da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "34821814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="8b2c4-102">Criar rotas de interregião de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b2c4-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b2c4-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8b2c4-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8b2c4-104">Uma *rota interregião de rede* define a rota entre um par de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="8b2c4-105">Cada par de regiões de rede em sua implantação de controle de admissão de chamadas requer uma rota interregion de rede.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="8b2c4-106">Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="8b2c4-107">Embora os links de região definam as limitações de largura de banda nas conexões entre regiões, uma rota entre regiões determina qual caminho vinculado a conexão passará de uma região para outra.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="8b2c4-108">Para obter detalhes sobre como trabalhar com rotas de interregião de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8b2c4-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8b2c4-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8b2c4-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8b2c4-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8b2c4-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8b2c4-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8b2c4-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8b2c4-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8b2c4-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="8b2c4-113">Na topologia de exemplo, as rotas interregion de rede devem ser definidas para cada um dos três pares de regiões: América do Norte/EMEA, EMEA/Ásia e América do Norte/Ásia-Pacífico.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="8b2c4-114">Para criar rotas de interregião de rede usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b2c4-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8b2c4-115">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8b2c4-116">Execute o cmdlet **New-CsNetworkInterRegionRoute** para definir as rotas necessárias.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="8b2c4-117">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="8b2c4-117">For example, run:</span></span>
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="8b2c4-118">A rota interregião da rede América do Norte/Ásia requer dois links de região de rede porque não há um link de região de rede direto entre eles.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="8b2c4-119">Para criar rotas de interregião de rede usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b2c4-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8b2c4-120">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8b2c4-121">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8b2c4-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8b2c4-122">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8b2c4-123">Clique no botão de navegações **Rota de Região**.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="8b2c4-124">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-124">Click **New**.</span></span>

5.  <span data-ttu-id="8b2c4-125">Na página **nova rota de região** , clique em **nome** e digite um nome para a rota interregião de rede.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="8b2c4-126">Clique na **região \#de rede 1**e, em seguida, clique em uma região de rede na lista que você deseja \#direcionar para a região de rede 2.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="8b2c4-127">Clique em **rede \#2**e, em seguida, clique em uma região de rede na lista que você deseja direcionar \#para a região de rede 1.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="8b2c4-128">Clique em **Adicionar** ao lado do campo de **links de região de rede** e, em seguida, adicione um link de região de rede que será usado na rota interregião de rede.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="8b2c4-129">Se você estiver criando uma rota para duas regiões de rede que não têm um link de região de rede direta de rede entre elas, deverá adicionar todos os links necessários para concluir a rota.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="8b2c4-130">Por exemplo, a rota de interregião da rede América do Norte/Ásia requer dois links de região de rede porque não há um link de região de rede direto entre eles.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="8b2c4-131">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-131">Click **Commit**.</span></span>

10. <span data-ttu-id="8b2c4-132">Para concluir a criação de rotas interregions de rede para a sua topologia, repita as etapas de 4 a 9 com configurações para outras rotas interregions de rede.</span><span class="sxs-lookup"><span data-stu-id="8b2c4-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

