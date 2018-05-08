---
title: Criar rotas inter-regionais de rede no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Criar ou modificar rotas interregional da rede, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 22e7872c6faa989779a93b6524c1740386f32d7d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-interregional-routes-in-skype-for-business-server-2015"></a><span data-ttu-id="10c30-103">Criar rotas inter-regionais de rede no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="10c30-103">Create network interregional routes in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="10c30-104">Criar ou modificar rotas interregional da rede, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="10c30-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="10c30-105">Uma rota de rede interregional define a rota entre um par de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="10c30-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="10c30-106">Cada par de regiões de rede em sua implantação do serviço de controle de admissão de chamadas exige uma rota entre regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="10c30-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="10c30-107">Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões.</span><span class="sxs-lookup"><span data-stu-id="10c30-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="10c30-108">Enquanto os vínculos de região definem limitações de largura de banda nas conexões entre regiões, uma rota entre regiões de rede determina o caminho vinculado que a conexão percorrerá de uma região à outra.</span><span class="sxs-lookup"><span data-stu-id="10c30-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="10c30-109">Na topologia de exemplo, as rotas entre regiões de rede devem ser definidas para cada um dos três pares de regiões: América do Norte/EMEA, EMEA/APAC e América do Norte/APAC.</span><span class="sxs-lookup"><span data-stu-id="10c30-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="10c30-110">Para criar rotas interregional de rede usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="10c30-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="10c30-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="10c30-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="10c30-112">Execute o cmdlet **New-CsNetworkInterRegionRoute** para definir as rotas necessárias.</span><span class="sxs-lookup"><span data-stu-id="10c30-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="10c30-113">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="10c30-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="10c30-114">A rota entre regiões de rede América do Norte/APAC requer dois links de regiões de rede porque não há um link de região de rede direta entre elas.</span><span class="sxs-lookup"><span data-stu-id="10c30-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="10c30-115">Para criar rotas interregional de rede usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="10c30-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="10c30-116">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="10c30-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="10c30-117">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="10c30-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="10c30-118">Clique no botão de navegações **Rota de Região**.</span><span class="sxs-lookup"><span data-stu-id="10c30-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="10c30-119">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="10c30-119">Click **New**.</span></span>
    
5. <span data-ttu-id="10c30-120">Na página **Nova Rota de Região**, clique em **Nome** e digite um nome para a rota entre regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="10c30-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="10c30-121">Clique em **Região de Rede 1** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="10c30-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="10c30-122">Clique em **Região de Rede 2** e clique em uma região de rede na lista que você deseja rotear para a Região de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="10c30-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="10c30-123">Clique em **Adicionar** próximo ao campo **Links de Região de Rede** e adicione um link de região de rede que será usado na rota entre regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="10c30-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="10c30-p103">Se você estiver criando uma rota para duas regiões de rede que não têm um link de região de rede direta de rede entre elas, deverá adicionar todos os links necessários para concluir a rota. Por exemplo, a rota entre regiões de rede América do Norte/APAC requer dois links de região de rede porque não há nenhum link de região de rede direta entre elas.</span><span class="sxs-lookup"><span data-stu-id="10c30-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="10c30-126">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="10c30-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="10c30-127">Para concluir a criação de rotas entre regiões de rede para sua topologia de rede, repita as etapas 4 a 9 com configurações de outras rotas entre regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="10c30-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="10c30-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="10c30-128">See also</span></span>

#### 

[<span data-ttu-id="10c30-129">New-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="10c30-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="10c30-130">Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="10c30-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="10c30-131">Set-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="10c30-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="10c30-132">Remove-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="10c30-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

