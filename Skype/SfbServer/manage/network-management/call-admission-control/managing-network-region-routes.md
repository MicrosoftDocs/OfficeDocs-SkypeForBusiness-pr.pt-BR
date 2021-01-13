---
title: Gerenciando rotas de região de rede
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Uma rota de região de rede define a rota entre um par de regiões de rede. Cada par de regiões de rede de sua implantação de controle de admissão de chamadas exige uma rota de região de rede.
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816431"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="380b9-104">Gerenciando roteamento de regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="380b9-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="380b9-105">Uma *rota de região de rede* define a rota entre um par de regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="380b9-106">Cada par de regiões de rede de sua implantação de controle de admissão de chamadas exige uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="380b9-107">Isso permite que todas as regiões de rede da implantação acessem todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="380b9-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="380b9-108">Use os procedimentos nesta arte para exibir, criar, modificar ou excluir rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="380b9-109">Exibir informações de rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="380b9-109">View network region route information</span></span> 

<span data-ttu-id="380b9-110">Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="380b9-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="380b9-111">Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra.</span><span class="sxs-lookup"><span data-stu-id="380b9-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="380b9-112">Use os procedimentos a seguir para exibir as rotas de região de rede existentes no Painel de Controle do Skype for Business Server ou no Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="380b9-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="380b9-113">Para exibir informações de rota de região de rede no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="380b9-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="380b9-114">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="380b9-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="380b9-115">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="380b9-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="380b9-116">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**</span><span class="sxs-lookup"><span data-stu-id="380b9-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="380b9-117">Na página **Rota de Região**, clique na rota de região que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="380b9-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="380b9-118">É possível ver apenas uma rota de região por vez.</span><span class="sxs-lookup"><span data-stu-id="380b9-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="380b9-119">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="380b9-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="380b9-120">Exibindo informações de rota de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="380b9-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="380b9-121">As informações de rota de região de rede podem ser exibidas usando o Windows PowerShell e o Get-CsNetworkInterRegionRoute cmdlet.</span><span class="sxs-lookup"><span data-stu-id="380b9-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="380b9-122">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="380b9-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="380b9-123">Para exibir informações de rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="380b9-123">To view network region route information</span></span>

  - <span data-ttu-id="380b9-124">Para exibir informações sobre todas as rotas de região de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="380b9-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="380b9-125">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="380b9-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="380b9-126">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="380b9-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="380b9-127">Criar ou modificar rotas de região de rede</span><span class="sxs-lookup"><span data-stu-id="380b9-127">Create or modify network region routes</span></span>

<span data-ttu-id="380b9-128">Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="380b9-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="380b9-129">Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra.</span><span class="sxs-lookup"><span data-stu-id="380b9-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="380b9-130">Você pode usar o Painel de Controle do Skype for Business Server para configurar rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="380b9-131">No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="380b9-132">Use este tópico para criar ou modificar uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="380b9-133">Para criar uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="380b9-133">To create a network region route</span></span>

1.  <span data-ttu-id="380b9-134">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="380b9-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="380b9-135">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="380b9-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="380b9-136">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**</span><span class="sxs-lookup"><span data-stu-id="380b9-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="380b9-137">Na página **Rota de Região**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="380b9-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="380b9-138">Em **Nova Rota de Região**, digite um valor no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="380b9-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="380b9-139">Esse valor deve ser exclusivo em sua implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="380b9-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="380b9-140">Na lista drop-down da Região **\# de rede 1,** selecione uma das duas regiões a serem conectadas por esta rota.</span><span class="sxs-lookup"><span data-stu-id="380b9-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="380b9-141">Na lista drop-down da Região de rede **\# 2,** selecione a outra região para essa rota.</span><span class="sxs-lookup"><span data-stu-id="380b9-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="380b9-142">Essa região deve ser diferente da região selecionada para a Região \# de rede 1.</span><span class="sxs-lookup"><span data-stu-id="380b9-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="380b9-p107">Use a caixa de listagem **Links de região de rede** para adicionar os links de região para a rota. Clique no botão **Adicionar** para exibir a página **Link de Região**. Clique em um link de região para adicionar a esta rota e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="380b9-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="380b9-146">Continue a clicar no botão **Adicionar** para adicionar mais links, ou selecione um link e clique em **Remover** para remover um link.</span><span class="sxs-lookup"><span data-stu-id="380b9-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="380b9-147">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="380b9-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="380b9-148">Para modificar uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="380b9-148">To modify a network region route</span></span>

1.  <span data-ttu-id="380b9-149">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="380b9-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="380b9-150">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="380b9-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="380b9-151">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**</span><span class="sxs-lookup"><span data-stu-id="380b9-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="380b9-152">Na página **Rota de Região**, clique no roteiro de região que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="380b9-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="380b9-153">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="380b9-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="380b9-154">Em **Editar rota de região**, você pode alterar as regiões associadas por essa rota e os links de região associados ao roteiro.</span><span class="sxs-lookup"><span data-stu-id="380b9-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="380b9-155">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="380b9-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="380b9-156">Excluir rotas de região de rede existentes</span><span class="sxs-lookup"><span data-stu-id="380b9-156">Delete existing network region routes</span></span>

<span data-ttu-id="380b9-157">Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="380b9-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="380b9-158">Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra.</span><span class="sxs-lookup"><span data-stu-id="380b9-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="380b9-159">Você pode usar o Painel de Controle do Skype for Business Server para configurar rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="380b9-160">No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="380b9-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="380b9-161">Use este tópico para excluir rotas de região de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="380b9-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="380b9-162">Para excluir uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="380b9-162">To delete a network region route</span></span>

1.  <span data-ttu-id="380b9-163">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="380b9-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="380b9-164">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="380b9-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="380b9-165">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Rota de Região.**</span><span class="sxs-lookup"><span data-stu-id="380b9-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="380b9-166">Na página **Rota de Região**, clique na rota de região que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="380b9-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="380b9-p109">Você pode excluir mais de uma rota de região por vez. Para fazer isso, pressione CTRL e selecione várias rotas de região mantendo pressionada a tecla CTRL. Para selecionar todas as rotas da região, clique em **Selecionar tudo** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="380b9-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="380b9-170">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="380b9-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="380b9-171">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="380b9-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="380b9-172">Confira também</span><span class="sxs-lookup"><span data-stu-id="380b9-172">See Also</span></span>

[<span data-ttu-id="380b9-173">Gerenciar regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="380b9-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="380b9-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="380b9-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="380b9-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="380b9-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="380b9-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="380b9-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="380b9-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="380b9-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
