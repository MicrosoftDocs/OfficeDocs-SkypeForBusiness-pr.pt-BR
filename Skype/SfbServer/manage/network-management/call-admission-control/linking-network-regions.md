---
title: Vinculando regiões de rede
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
description: 'Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas. '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816461"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="3b1d6-103">Vincular regiões de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b1d6-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="3b1d6-104">Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3b1d6-105">Use as seções deste artigo para exibir informações de link de região nova ou configurar ou excluir links de região netwrok.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="3b1d6-106">Exibir informações de link de região de rede</span><span class="sxs-lookup"><span data-stu-id="3b1d6-106">View network region link information</span></span> 

<span data-ttu-id="3b1d6-107">Você pode visualizar os links entre duas regiões de redes como parte do controle de admissão de chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="3b1d6-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3b1d6-108">Regiões dentro de uma rede são vinculadas por conectividade de WAN física.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="3b1d6-109">Você pode usar o Painel de Controle do Skype for Business Server para exibir um link existente entre duas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="3b1d6-110">Para exibir um link de região de rede no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3b1d6-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3b1d6-111">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b1d6-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3b1d6-113">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**</span><span class="sxs-lookup"><span data-stu-id="3b1d6-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3b1d6-114">Na página **Link da região**, clique no link da região que você deseja ver.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="3b1d6-115">Você pode ver informações somente sobre um link da região por vez.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="3b1d6-116">No menu **Editar**, selecione **Mostras detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3b1d6-117">Exibir informações de link de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b1d6-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3b1d6-118">Você pode exibir links de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink.**</span><span class="sxs-lookup"><span data-stu-id="3b1d6-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="3b1d6-119">Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="3b1d6-120">Para ver informações do link de região de rede</span><span class="sxs-lookup"><span data-stu-id="3b1d6-120">To view network region link information</span></span>

  - <span data-ttu-id="3b1d6-121">Para exibir informações sobre todos os links de região de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="3b1d6-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="3b1d6-122">Esse comando retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="3b1d6-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="3b1d6-123">Para detalhes, consulte [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="3b1d6-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="3b1d6-124">Configurar links de região de rede</span><span class="sxs-lookup"><span data-stu-id="3b1d6-124">Configure network region links</span></span> 

<span data-ttu-id="3b1d6-125">Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3b1d6-126">Regiões dentro de uma rede são vinculadas por conectividade de WAN física.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="3b1d6-127">Você pode usar o Painel de Controle do Skype for Business Server para definir um link entre duas regiões de rede e definir as limitações de largura de banda em conexões de áudio e vídeo entre essas regiões.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="3b1d6-128">Para criar um link de região de rede</span><span class="sxs-lookup"><span data-stu-id="3b1d6-128">To create a network region link</span></span>

1.  <span data-ttu-id="3b1d6-129">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b1d6-130">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3b1d6-131">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**</span><span class="sxs-lookup"><span data-stu-id="3b1d6-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3b1d6-132">Na página **Link de Região**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="3b1d6-133">Em **Novo Link de Região**, digite um valor no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="3b1d6-134">Esse valor deve ser exclusivo em sua implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="3b1d6-135">Na lista **drop-down da Região de rede \# 1,** selecione uma das duas regiões a serem vinculadas.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="3b1d6-136">Na lista **da região de rede \# 2,** selecione a outra região a ser vinculada.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="3b1d6-137">Essa região deve ser diferente da região selecionada para a Região \# de rede 1.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="3b1d6-138">(Opcional) Se você desejar colocar limites de largura de banda em chamadas de áudio e vídeo entre essas regiões, selecione um perfil de política de largura de banda na lista suspensa **Política de largura de banda**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="3b1d6-139">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="3b1d6-140">Para modificar um link de região de rede</span><span class="sxs-lookup"><span data-stu-id="3b1d6-140">To modify a network region link</span></span>

1.  <span data-ttu-id="3b1d6-141">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b1d6-142">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3b1d6-143">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**</span><span class="sxs-lookup"><span data-stu-id="3b1d6-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3b1d6-144">Na página **Link de Região**, clique no link de região que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="3b1d6-145">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3b1d6-146">Em **Editar Link de Região**, você pode modificar as regiões que estão vinculadas ou o perfil de política de largura de banda para este link.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="3b1d6-147">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="3b1d6-148">Excluir links de região de rede</span><span class="sxs-lookup"><span data-stu-id="3b1d6-148">Delete network region links</span></span>

<span data-ttu-id="3b1d6-149">Você pode configurar links entre duas regiões de rede como parte do controle de admissão de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3b1d6-150">Regiões dentro de uma rede são vinculadas por conectividade de WAN física.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="3b1d6-151">Você pode usar o Painel de Controle do Skype for Business Server para excluir um link existente entre duas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="3b1d6-152">Para excluir um link de região de rede</span><span class="sxs-lookup"><span data-stu-id="3b1d6-152">To delete a network region link</span></span>

1.  <span data-ttu-id="3b1d6-153">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b1d6-154">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3b1d6-155">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Link de Região.**</span><span class="sxs-lookup"><span data-stu-id="3b1d6-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3b1d6-156">Na página **Link de** Região, clique no link de região que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="3b1d6-157">Você pode excluir mais de um link de região por vez.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="3b1d6-158">Para fazer isso, pressione CTRL e selecione vários links de região mantendo pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="3b1d6-159">Ou, para selecionar todos os links de região, clique <STRONG>em Selecionar tudo</STRONG> no menu Editar. <STRONG></STRONG></span><span class="sxs-lookup"><span data-stu-id="3b1d6-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="3b1d6-160">No menu **Editar,** selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="3b1d6-161">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b1d6-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="3b1d6-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b1d6-162">See Also</span></span>

[<span data-ttu-id="3b1d6-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3b1d6-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="3b1d6-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3b1d6-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="3b1d6-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3b1d6-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="3b1d6-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3b1d6-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
