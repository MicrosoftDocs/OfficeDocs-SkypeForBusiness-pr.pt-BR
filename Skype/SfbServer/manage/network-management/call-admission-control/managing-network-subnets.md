---
title: Gerenciar subredes
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes. Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell.
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198905"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="b0989-104">Gerenciar sub-redes de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b0989-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="b0989-105">Você pode usar ambos o Skype para painel de controle do Business Server ou o Skype do Shell de gerenciamento do servidor de negócios para gerenciar sub-redes da rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="b0989-106">Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="b0989-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="b0989-107">Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0989-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="b0989-108">Use as seções deste artigo para exibir informações de sub-rede de rede ou criar, modificar ou excluir subredes.</span><span class="sxs-lookup"><span data-stu-id="b0989-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="b0989-109">Exibir informações de sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="b0989-109">View network subnet information</span></span> 

<span data-ttu-id="b0989-110">Você pode usar o procedimento a seguir para visualizar uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="b0989-111">Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="b0989-112">Para visualizar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="b0989-112">To view a network subnet</span></span>

1.  <span data-ttu-id="b0989-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b0989-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0989-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b0989-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b0989-115">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.</span><span class="sxs-lookup"><span data-stu-id="b0989-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b0989-116">Na página **subrede** , clique na sub-rede que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="b0989-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="b0989-117">Você só pode exibir uma sub-rede por vez.</span><span class="sxs-lookup"><span data-stu-id="b0989-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="b0989-118">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b0989-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b0989-119">Exibir informações de configuração da sub-rede de rede pelos cmdlets usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0989-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b0989-120">Informações de sub-rede de rede podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="b0989-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="b0989-121">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0989-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="b0989-122">Para exibir informações de sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="b0989-122">To view network subnet information</span></span>

  - <span data-ttu-id="b0989-123">Para exibir informações sobre todas as sub-redes da rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="b0989-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="b0989-124">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="b0989-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="b0989-125">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="b0989-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="b0989-126">Criar ou modificar subredes</span><span class="sxs-lookup"><span data-stu-id="b0989-126">Create or modify network subnets</span></span> 

<span data-ttu-id="b0989-127">Uma sub-rede de rede deve ser associada um site de rede para fins de determinar a localização geográfica do host que pertencem a esta sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="b0989-128">Você pode usar o Skype para painel de controle do Business Server para configurar sub-redes.</span><span class="sxs-lookup"><span data-stu-id="b0989-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="b0989-129">Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="b0989-130">Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="b0989-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="b0989-131">Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0989-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b0989-132">A partir daí, você pode chamar **New-CsNetworkSubnet** junto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0989-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="b0989-133">Usando esses cmdlets juntos, você pode ler configurações de sub-rede de um arquivo de valores separados por vírgula (. csv) e criar várias sub-redes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b0989-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="b0989-134">Para obter exemplos de como criar sub-redes de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="b0989-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="b0989-135">Para criar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="b0989-135">To create a network subnet</span></span>

1.  <span data-ttu-id="b0989-136">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b0989-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0989-137">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b0989-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b0989-138">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.</span><span class="sxs-lookup"><span data-stu-id="b0989-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b0989-139">Na página **subrede** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="b0989-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="b0989-140">Na **Nova sub-rede**, insira um valor no campo **ID de sub-rede** .</span><span class="sxs-lookup"><span data-stu-id="b0989-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="b0989-141">Isso deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="b0989-142">No campo **máscara** , insira um valor numérico de 1 a 32.</span><span class="sxs-lookup"><span data-stu-id="b0989-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b0989-143">Esse valor é o bitmask que deve ser aplicada à sub-rede que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="b0989-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="b0989-144">**ID do site de rede**, selecione o site ao qual esta sub-rede pertence.</span><span class="sxs-lookup"><span data-stu-id="b0989-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="b0989-145">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa sub-rede que não pode ser expressa somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="b0989-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="b0989-146">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b0989-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="b0989-147">Para modificar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="b0989-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="b0989-148">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b0989-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0989-149">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b0989-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b0989-150">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.</span><span class="sxs-lookup"><span data-stu-id="b0989-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b0989-151">Na página **subrede** , clique na sub-rede que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="b0989-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="b0989-152">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b0989-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b0989-153">Na página **Editar sub-rede** , você pode modificar o bitmask, o site de rede associado ou a descrição.</span><span class="sxs-lookup"><span data-stu-id="b0989-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="b0989-154">Se você modificar o bitmask, tenha em mente que a ID de sub-rede ainda deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="b0989-155">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b0989-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="b0989-156">Excluir subredes</span><span class="sxs-lookup"><span data-stu-id="b0989-156">Delete network subnets</span></span>

<span data-ttu-id="b0989-157">Você pode usar o procedimento a seguir para excluir uma sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="b0989-158">Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="b0989-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="b0989-159">Na maioria das implantações do Skype para Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="b0989-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="b0989-160">Por esse motivo, geralmente é melhor configurar sub-redes a partir do Skype para Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0989-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b0989-161">A partir daí, você pode chamar **New-CsNetworkSubnet** junto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0989-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="b0989-162">Usando esses cmdlets juntos, você pode ler configurações de sub-rede de um arquivo de valores separados por vírgula (. csv) e criar várias sub-redes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b0989-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="b0989-163">Para obter exemplos de como criar sub-redes de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="b0989-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="b0989-164">Para excluir uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="b0989-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="b0989-165">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b0989-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0989-166">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b0989-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b0989-167">Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **subrede**.</span><span class="sxs-lookup"><span data-stu-id="b0989-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="b0989-168">Na página **subrede** , clique na sub-rede que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="b0989-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="b0989-169">Você pode excluir mais de uma sub-rede por vez.</span><span class="sxs-lookup"><span data-stu-id="b0989-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="b0989-170">Para fazer isso, pressione CTRL e selecione várias sub-redes, mantendo pressionada a tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="b0989-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="b0989-171">Ou, para selecionar todas as sub-redes, clique em **Selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="b0989-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="b0989-172">No menu **Editar** , clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b0989-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="b0989-173">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0989-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="b0989-174">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b0989-174">See Also</span></span>

[<span data-ttu-id="b0989-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b0989-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="b0989-176">Set-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="b0989-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="b0989-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b0989-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="b0989-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="b0989-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
