---
title: Gerenciando sub-redes de rede
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
description: Na maioria das implantações do Skype for Business Server, onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server.
ms.openlocfilehash: ef771ad78f00085374038203e1049790a9179e88
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122435"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="5d1ca-104">Gerenciando sub-redes de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5d1ca-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="5d1ca-105">Você pode usar o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server para gerenciar sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="5d1ca-106">Na maioria das implantações do Skype for Business Server, onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5d1ca-107">Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="5d1ca-108">Use as seções deste artigo para exibir informações de sub-rede de rede ou criar, modificar ou excluir sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="5d1ca-109">Exibir informações da sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-109">View network subnet information</span></span> 

<span data-ttu-id="5d1ca-110">Você pode utilizar o seguinte procedimento para visualizar uma sub-rede da rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="5d1ca-111">No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="5d1ca-112">Para visualizar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-112">To view a network subnet</span></span>

1.  <span data-ttu-id="5d1ca-113">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d1ca-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5d1ca-115">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5d1ca-116">Na página de **Sub-rede**, clique na sub-rede que deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5d1ca-117">Você só pode visualizar uma sub-rede por vez.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="5d1ca-118">No painel **Ações**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5d1ca-119">Exibir informações de configuração de sub-rede de rede usando Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="5d1ca-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5d1ca-120">As informações da sub-rede de rede podem ser exibidas usando Windows PowerShell e o cmdlet Get-CsNetworkSubnet rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="5d1ca-121">Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="5d1ca-122">Para exibir informações de sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-122">To view network subnet information</span></span>

  - <span data-ttu-id="5d1ca-123">Para exibir informações sobre todas as sub-redes de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="5d1ca-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="5d1ca-124">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d1ca-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="5d1ca-125">Para mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="5d1ca-125">For more information, see the help topic for the [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="5d1ca-126">Criar ou modificar sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-126">Create or modify network subnets</span></span> 

<span data-ttu-id="5d1ca-127">É necessário associar uma subrede da rede com um site de rede para fins de determinar o local geográfico do host que pertence a esta subrede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="5d1ca-128">Você pode usar o Painel de Controle do Skype for Business Server para configurar sub-redes.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="5d1ca-129">No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="5d1ca-130">Na maioria das implantações do Skype for Business Server, onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5d1ca-131">Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5d1ca-132">A partir daí, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Windows PowerShell Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="5d1ca-133">Usando estes cmdlets em conjunto, é possível ler nas configurações de subrede de um arquivo de valores separados por vírgula (.csv) e criar várias subredes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="5d1ca-134">Para obter exemplos de como criar sub-redes a partir de um arquivo .csv, consulte [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="5d1ca-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="5d1ca-135">Para criar uma sub-rede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-135">To create a network subnet</span></span>

1.  <span data-ttu-id="5d1ca-136">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d1ca-137">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5d1ca-138">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5d1ca-139">Na página **Sub-rede** clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="5d1ca-p107">Em **Nova Sub-rede**, digite um valor no campo **ID da sub-rede**. Esse valor deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereço IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="5d1ca-142">No campo **Máscara**, digite um valor numérico de 1 a 32.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="5d1ca-143">Este valor é o bitmask que será aplicado na sub-rede criada.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="5d1ca-144">Em **ID do site da rede**, selecione o site ao qual a sub-rede pertence.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="5d1ca-145">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações essa sub-rede que não pode ser expressa somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="5d1ca-146">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="5d1ca-147">Para modificar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="5d1ca-148">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d1ca-149">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5d1ca-150">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5d1ca-151">Na página **Sub-rede**, clique na sub-rede que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="5d1ca-152">No menu **Editar**, clique **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5d1ca-p108">Na página **Editar sub-rede**, é possível modificar o bitmask, o local de rede associado ou a descrição. Se for mudar o bitmask, tenha em mente que o ID da sub-rede deve ser ainda o primeiro endereço do intervalo de endereço IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="5d1ca-155">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="5d1ca-156">Excluir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-156">Delete network subnets</span></span>

<span data-ttu-id="5d1ca-157">É possível usar o seguinte procedimento para excluir uma subrede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="5d1ca-158">No Painel de Controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="5d1ca-159">Na maioria das implantações do Skype for Business Server, onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5d1ca-160">Por isso, geralmente é melhor configurar sub-redes do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5d1ca-161">A partir daí, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Windows PowerShell Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="5d1ca-162">Usando estes cmdlets em conjunto, é possível ler nas configurações de subrede de um arquivo de valores separados por vírgula (.csv) e criar várias subredes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="5d1ca-163">Para ver exemplos de como criar subredes de um arquivo .csv, consulte [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="5d1ca-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="5d1ca-164">Para excluir uma subrede</span><span class="sxs-lookup"><span data-stu-id="5d1ca-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="5d1ca-165">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5d1ca-166">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5d1ca-167">Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5d1ca-168">Na página **Subrede**, clique na subrede que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5d1ca-p111">Você pode excluir mais de uma subrede simultaneamente. Para isso, pressione a tecla CTRL e selecione várias subredes mantendo a tecla CTRL pressionada. Em alternativa, para selecionar todas as subredes, clique em **Selecionar todas** no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="5d1ca-172">No menu **Editar**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="5d1ca-173">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d1ca-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="5d1ca-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="5d1ca-174">See Also</span></span>

[<span data-ttu-id="5d1ca-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5d1ca-175">New-CsNetworkSubnet</span></span>](/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="5d1ca-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5d1ca-176">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="5d1ca-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5d1ca-177">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="5d1ca-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5d1ca-178">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/Get-CsNetworkSubnet)