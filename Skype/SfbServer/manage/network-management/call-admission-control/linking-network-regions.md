---
title: Vinculação de regiões de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC). '
ms.openlocfilehash: 30d4a020826b24c3615ce059809645481466efc3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888349"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="d8be7-103">Vincular regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d8be7-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="d8be7-104">Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="d8be7-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="d8be7-105">Use as seções deste artigo para exibir informações de link de região newtwork ou configurar ou excluir links de região de rede.</span><span class="sxs-lookup"><span data-stu-id="d8be7-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="d8be7-106">Exibir informações de link de região de rede</span><span class="sxs-lookup"><span data-stu-id="d8be7-106">View network region link information</span></span> 

<span data-ttu-id="d8be7-107">Você pode exibir links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="d8be7-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="d8be7-108">Regiões dentro de uma rede são vinculadas por meio da conectividade de rede (WAN) de longa distância físico.</span><span class="sxs-lookup"><span data-stu-id="d8be7-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="d8be7-109">Você pode usar o Skype para painel de controle do Business Server para exibir um link existente entre duas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="d8be7-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="d8be7-110">Para exibir um link de região de rede no Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="d8be7-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d8be7-111">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d8be7-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8be7-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d8be7-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8be7-113">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="d8be7-114">Na página **Link de região** , clique no link de região que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d8be7-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="d8be7-115">Você só pode exibir informações sobre um link da região por vez.</span><span class="sxs-lookup"><span data-stu-id="d8be7-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="d8be7-116">No menu **Editar** , selecione **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d8be7-117">Exibir informações de link de região de rede usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8be7-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d8be7-118">Você pode exibir os links de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="d8be7-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="d8be7-119">Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8be7-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="d8be7-120">Para exibir informações de link de região de rede</span><span class="sxs-lookup"><span data-stu-id="d8be7-120">To view network region link information</span></span>

  - <span data-ttu-id="d8be7-121">Para exibir informações sobre todos os links da região de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d8be7-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="d8be7-122">Este comando retorna informações semelhantes para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d8be7-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="d8be7-123">Para obter detalhes, consulte [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="d8be7-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="d8be7-124">Configurar links de região de rede</span><span class="sxs-lookup"><span data-stu-id="d8be7-124">Configure network region links</span></span> 

<span data-ttu-id="d8be7-125">Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="d8be7-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="d8be7-126">Regiões dentro de uma rede são vinculadas por meio da conectividade de rede (WAN) de longa distância físico.</span><span class="sxs-lookup"><span data-stu-id="d8be7-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="d8be7-127">Você pode usar o Skype para painel de controle do Business Server para definir um link entre duas regiões de rede e definir as limitações de largura de banda em conexões de áudio e vídeo entre essas regiões.</span><span class="sxs-lookup"><span data-stu-id="d8be7-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="d8be7-128">Para criar um link de região de rede</span><span class="sxs-lookup"><span data-stu-id="d8be7-128">To create a network region link</span></span>

1.  <span data-ttu-id="d8be7-129">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d8be7-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8be7-130">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d8be7-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8be7-131">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="d8be7-132">Na página **Link de região** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="d8be7-133">Em **Novo Link de região**, digite um valor no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="d8be7-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="d8be7-134">Este valor deve ser exclusivo dentro de sua Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d8be7-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="d8be7-135">Da **região de rede \#1** lista suspensa, selecione uma das duas regiões a serem vinculadas.</span><span class="sxs-lookup"><span data-stu-id="d8be7-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="d8be7-136">Da **região de rede \#2** lista suspensa, selecione a outra região a serem vinculadas.</span><span class="sxs-lookup"><span data-stu-id="d8be7-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="d8be7-137">Essa região deve ser diferente da região selecionada para a região de rede \#1.</span><span class="sxs-lookup"><span data-stu-id="d8be7-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="d8be7-138">(Opcional) Se você deseja colocar as limitações de largura de banda em chamadas de áudio ou vídeos entre essas regiões, selecione um perfil de política de largura de banda na lista suspensa **política de largura de banda** .</span><span class="sxs-lookup"><span data-stu-id="d8be7-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="d8be7-139">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="d8be7-140">Para modificar um link de região de rede</span><span class="sxs-lookup"><span data-stu-id="d8be7-140">To modify a network region link</span></span>

1.  <span data-ttu-id="d8be7-141">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d8be7-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8be7-142">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d8be7-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8be7-143">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="d8be7-144">Na página **Link de região** , clique no link de região que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="d8be7-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="d8be7-145">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d8be7-146">Em **Editar Link de região**, você pode modificar as regiões que estão vinculadas ou o perfil de política de largura de banda para este link.</span><span class="sxs-lookup"><span data-stu-id="d8be7-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="d8be7-147">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="d8be7-148">Excluir links de região de rede</span><span class="sxs-lookup"><span data-stu-id="d8be7-148">Delete network region links</span></span>

<span data-ttu-id="d8be7-149">Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="d8be7-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="d8be7-150">Regiões dentro de uma rede são vinculadas por meio da conectividade de rede (WAN) de longa distância físico.</span><span class="sxs-lookup"><span data-stu-id="d8be7-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="d8be7-151">Você pode usar o Skype para painel de controle do Business Server para excluir um link existente entre duas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="d8be7-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="d8be7-152">Para excluir um link de região de rede</span><span class="sxs-lookup"><span data-stu-id="d8be7-152">To delete a network region link</span></span>

1.  <span data-ttu-id="d8be7-153">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d8be7-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8be7-154">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d8be7-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8be7-155">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique no **Link de região**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="d8be7-156">Na página **Link de região** , clique no link de região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="d8be7-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="d8be7-157">Você pode excluir mais de um link de região por vez.</span><span class="sxs-lookup"><span data-stu-id="d8be7-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="d8be7-158">Para fazer isso, pressione CTRL e selecione vários links de região, mantendo pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="d8be7-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="d8be7-159">Ou, para selecionar todos os links de região, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d8be7-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="d8be7-160">No menu **Editar** , selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="d8be7-161">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8be7-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="d8be7-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="d8be7-162">See Also</span></span>

[<span data-ttu-id="d8be7-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="d8be7-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="d8be7-164">Set-CsNetworkRegionLink.</span><span class="sxs-lookup"><span data-stu-id="d8be7-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="d8be7-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="d8be7-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="d8be7-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="d8be7-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
