---
title: Gerenciando sub-redes de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes. Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server.
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279477"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="2d901-104">Gerenciar sub-redes de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2d901-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="2d901-105">Você pode usar o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server para gerenciar sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="2d901-106">Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="2d901-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="2d901-107">Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d901-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="2d901-108">Use as seções deste artigo para exibir as informações de sub-rede da rede ou criar, modificar ou excluir sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="2d901-109">Exibir informações de sub-rede da rede</span><span class="sxs-lookup"><span data-stu-id="2d901-109">View network subnet information</span></span> 

<span data-ttu-id="2d901-110">Você pode usar o procedimento a seguir para exibir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="2d901-111">No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="2d901-112">Para exibir uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="2d901-112">To view a network subnet</span></span>

1.  <span data-ttu-id="2d901-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2d901-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d901-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d901-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2d901-115">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="2d901-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="2d901-116">Na página **sub-rede** , clique na sub-rede que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="2d901-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="2d901-117">Você só pode exibir uma sub-rede de cada vez.</span><span class="sxs-lookup"><span data-stu-id="2d901-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="2d901-118">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="2d901-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d901-119">Exibir informações de configuração de sub-rede de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d901-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2d901-120">As informações de sub-rede da rede podem ser visualizadas usando o Windows PowerShell e o cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="2d901-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="2d901-121">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d901-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="2d901-122">Para ver as informações de sub-rede da rede</span><span class="sxs-lookup"><span data-stu-id="2d901-122">To view network subnet information</span></span>

  - <span data-ttu-id="2d901-123">Para ver as informações sobre todas as suas sub-redes de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="2d901-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="2d901-124">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="2d901-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="2d901-125">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="2d901-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="2d901-126">Criar ou modificar sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="2d901-126">Create or modify network subnets</span></span> 

<span data-ttu-id="2d901-127">Uma sub-rede de rede deve estar associada a um site de rede para fins de determinar a localização geográfica do host pertencente a essa sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="2d901-128">Você pode usar o painel de controle do Skype for Business Server para configurar sub-redes.</span><span class="sxs-lookup"><span data-stu-id="2d901-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="2d901-129">No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="2d901-130">Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="2d901-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="2d901-131">Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d901-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2d901-132">Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d901-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="2d901-133">Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="2d901-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="2d901-134">Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="2d901-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="2d901-135">Para criar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="2d901-135">To create a network subnet</span></span>

1.  <span data-ttu-id="2d901-136">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2d901-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d901-137">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d901-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2d901-138">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="2d901-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="2d901-139">Na página **sub-rede** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="2d901-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="2d901-140">Em **nova sub-rede**, insira um valor no campo **subnet ID** .</span><span class="sxs-lookup"><span data-stu-id="2d901-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="2d901-141">Deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="2d901-142">No campo **máscara** , insira um valor numérico de 1 a 32.</span><span class="sxs-lookup"><span data-stu-id="2d901-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2d901-143">Esse valor é o bitmask que deve ser aplicado à sub-rede que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="2d901-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="2d901-144">Em **ID de site de rede**, selecione o site ao qual esta sub-rede pertence.</span><span class="sxs-lookup"><span data-stu-id="2d901-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="2d901-145">Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa sub-rede que não pode ser expressa apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="2d901-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="2d901-146">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2d901-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="2d901-147">Para modificar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="2d901-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="2d901-148">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2d901-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d901-149">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d901-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2d901-150">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="2d901-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="2d901-151">Na página **sub-rede** , clique na sub-rede que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="2d901-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="2d901-152">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="2d901-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="2d901-153">Na página **Editar sub-rede** , você pode modificar o bitmask, o site de rede associado ou a descrição.</span><span class="sxs-lookup"><span data-stu-id="2d901-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="2d901-154">Se você modificar o bitmask, lembre-se de que a identificação da sub-rede ainda deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="2d901-155">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2d901-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="2d901-156">Excluir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="2d901-156">Delete network subnets</span></span>

<span data-ttu-id="2d901-157">Você pode usar o procedimento a seguir para excluir uma sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="2d901-158">No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="2d901-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="2d901-159">Na maioria das implantações do Skype for Business Server onde o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="2d901-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="2d901-160">Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d901-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2d901-161">Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d901-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="2d901-162">Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="2d901-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="2d901-163">Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="2d901-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="2d901-164">Para excluir uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="2d901-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="2d901-165">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2d901-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d901-166">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d901-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2d901-167">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="2d901-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="2d901-168">Na página **sub-rede** , clique na sub-rede que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="2d901-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="2d901-169">Você pode excluir mais de uma sub-rede de cada vez.</span><span class="sxs-lookup"><span data-stu-id="2d901-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="2d901-170">Para fazer isso, pressione CTRL e selecione várias sub-redes enquanto mantém a tecla CTRL pressionada.</span><span class="sxs-lookup"><span data-stu-id="2d901-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="2d901-171">Ou, para selecionar todas as sub-redes, clique em **selecionar tudo** no menu **Editar** .</span><span class="sxs-lookup"><span data-stu-id="2d901-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="2d901-172">No menu **Editar** , clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="2d901-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="2d901-173">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d901-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="2d901-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="2d901-174">See Also</span></span>

[<span data-ttu-id="2d901-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="2d901-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="2d901-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="2d901-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="2d901-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="2d901-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="2d901-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="2d901-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
