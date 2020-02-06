---
title: Gerenciando rotas de região de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Uma rota de região de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamadas requer uma rota de região de rede.
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817490"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="65a6e-104">Gerenciar roteamento de regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65a6e-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="65a6e-105">Uma *rota de região de rede* define a rota entre um par de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="65a6e-106">Cada par de regiões de rede em sua implantação de controle de admissão de chamadas requer uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="65a6e-107">Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões.</span><span class="sxs-lookup"><span data-stu-id="65a6e-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="65a6e-108">Use os procedimentos deste Artilce para exibir, criar, modificar ou excluir rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="65a6e-109">Exibir informações de rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="65a6e-109">View network region route information</span></span> 

<span data-ttu-id="65a6e-110">Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="65a6e-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="65a6e-111">Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra.</span><span class="sxs-lookup"><span data-stu-id="65a6e-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="65a6e-112">Use os procedimentos a seguir para exibir as rotas de região de rede existentes no painel de controle do Skype for Business Server ou Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65a6e-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="65a6e-113">Para ver as informações de rota de região de rede no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65a6e-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="65a6e-114">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="65a6e-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65a6e-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65a6e-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65a6e-116">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="65a6e-117">Na página **rota de região** , clique na rota de região que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="65a6e-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="65a6e-118">Você só pode exibir uma rota de região por vez.</span><span class="sxs-lookup"><span data-stu-id="65a6e-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="65a6e-119">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="65a6e-120">Exibir informações de rota de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a6e-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="65a6e-121">As informações de rota de região de rede podem ser visualizadas usando o Windows PowerShell e o cmdlet Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="65a6e-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="65a6e-122">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65a6e-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="65a6e-123">Para exibir as informações de rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="65a6e-123">To view network region route information</span></span>

  - <span data-ttu-id="65a6e-124">Para ver as informações sobre todas as suas rotas de região de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="65a6e-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="65a6e-125">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="65a6e-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="65a6e-126">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="65a6e-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="65a6e-127">Criar ou modificar rotas de região de rede</span><span class="sxs-lookup"><span data-stu-id="65a6e-127">Create or modify network region routes</span></span>

<span data-ttu-id="65a6e-128">Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="65a6e-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="65a6e-129">Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra.</span><span class="sxs-lookup"><span data-stu-id="65a6e-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="65a6e-130">Você pode usar o painel de controle do Skype for Business Server para configurar rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="65a6e-131">No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="65a6e-132">Use este tópico para criar ou modificar uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="65a6e-133">Para criar uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="65a6e-133">To create a network region route</span></span>

1.  <span data-ttu-id="65a6e-134">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="65a6e-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65a6e-135">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65a6e-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65a6e-136">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="65a6e-137">Na página **rota de região** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="65a6e-138">Em **nova rota de região**, digite um valor no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="65a6e-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="65a6e-139">Esse valor deve ser exclusivo na implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65a6e-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="65a6e-140">Na lista suspensa **região \#de rede 1** , selecione uma das duas regiões a serem conectadas por essa rota.</span><span class="sxs-lookup"><span data-stu-id="65a6e-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="65a6e-141">Na lista suspensa **região \#de rede 2** , selecione a outra região para esta rota.</span><span class="sxs-lookup"><span data-stu-id="65a6e-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="65a6e-142">Esta região deve ser diferente da região selecionada para a região \#de rede 1.</span><span class="sxs-lookup"><span data-stu-id="65a6e-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="65a6e-143">Use a caixa de listagem de **links de região de rede** para adicionar links de região ao roteiro.</span><span class="sxs-lookup"><span data-stu-id="65a6e-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="65a6e-144">Clique no botão **Adicionar** para exibir a página de **link de região** .</span><span class="sxs-lookup"><span data-stu-id="65a6e-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="65a6e-145">Clique em um link de região para adicionar a essa rota e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="65a6e-146">Continue a clicar no botão **Adicionar** para adicionar mais links ou selecionar um link e clicar em **remover** para remover um link.</span><span class="sxs-lookup"><span data-stu-id="65a6e-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="65a6e-147">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="65a6e-148">Para modificar uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="65a6e-148">To modify a network region route</span></span>

1.  <span data-ttu-id="65a6e-149">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="65a6e-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65a6e-150">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65a6e-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65a6e-151">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="65a6e-152">Na página **rota de região** , clique na rota de região que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="65a6e-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="65a6e-153">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="65a6e-154">Em **Editar rota de região**, você pode modificar as regiões Unidas por essa rota e os links de região associados à rota.</span><span class="sxs-lookup"><span data-stu-id="65a6e-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="65a6e-155">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="65a6e-156">Excluir rotas de região de rede existentes</span><span class="sxs-lookup"><span data-stu-id="65a6e-156">Delete existing network region routes</span></span>

<span data-ttu-id="65a6e-157">Todas as regiões em uma configuração de controle de admissão de chamadas (CAC) devem ter alguma maneira de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="65a6e-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="65a6e-158">Enquanto links de região definem as limitações de largura de banda nas conexões entre regiões e também representam os links físicos, uma rota determina qual caminho vinculado a conexão passará de uma região para outra.</span><span class="sxs-lookup"><span data-stu-id="65a6e-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="65a6e-159">Você pode usar o painel de controle do Skype for Business Server para configurar rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="65a6e-160">No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="65a6e-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="65a6e-161">Use este tópico para excluir as rotas de região de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="65a6e-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="65a6e-162">Para excluir uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="65a6e-162">To delete a network region route</span></span>

1.  <span data-ttu-id="65a6e-163">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="65a6e-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65a6e-164">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65a6e-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65a6e-165">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **rota de região**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="65a6e-166">Na página **rota de região** , clique na rota de região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="65a6e-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="65a6e-167">Você pode excluir mais de uma rota de região por vez.</span><span class="sxs-lookup"><span data-stu-id="65a6e-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="65a6e-168">Para fazer isso, pressione CTRL e selecione várias rotas de região enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="65a6e-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="65a6e-169">Ou, para selecionar todas as rotas de região, clique em **selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="65a6e-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="65a6e-170">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="65a6e-171">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="65a6e-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="65a6e-172">Confira também</span><span class="sxs-lookup"><span data-stu-id="65a6e-172">See Also</span></span>

[<span data-ttu-id="65a6e-173">Gerenciar regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65a6e-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="65a6e-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="65a6e-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="65a6e-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="65a6e-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="65a6e-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="65a6e-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="65a6e-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="65a6e-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
