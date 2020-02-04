---
title: 'Lync Server 2013: criar ou modificar sub-redes de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d743e5cdbe8dc7f200175b74f55b1b3d003e769
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="17839-102">Criar ou modificar sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17839-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17839-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="17839-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="17839-104">Uma sub-rede de rede deve estar associada a um site de rede para fins de determinar a localização geográfica do host pertencente a essa sub-rede.</span><span class="sxs-lookup"><span data-stu-id="17839-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="17839-105">Você pode usar o painel de controle do Lync Server para configurar sub-redes.</span><span class="sxs-lookup"><span data-stu-id="17839-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="17839-106">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="17839-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="17839-107">Para obter detalhes sobre como excluir sub-redes de rede, consulte [excluindo sub-redes de rede no Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="17839-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="17839-108">Na maioria das implantações do Microsoft Lync Server 2013 em que o controle de admissão de chamadas (CAC) é implementado, normalmente há um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="17839-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="17839-109">Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17839-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="17839-110">Em seguida, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17839-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="17839-111">Ao usar esses cmdlets juntos, você pode ler as configurações de sub-rede a partir de um arquivo de valores separados por vírgulas (. csv) e criar várias sub-redes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="17839-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="17839-112">Para obter exemplos de como criar sub-redes a partir de um arquivo. csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="17839-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="17839-113">Para criar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="17839-113">To create a network subnet</span></span>

1.  <span data-ttu-id="17839-114">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="17839-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17839-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17839-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17839-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="17839-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17839-117">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="17839-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="17839-118">Na página **sub-rede** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="17839-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="17839-119">Em **nova sub-rede**, insira um valor no campo **subnet ID** .</span><span class="sxs-lookup"><span data-stu-id="17839-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="17839-120">Deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="17839-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="17839-121">No campo **máscara** , insira um valor numérico de 1 a 32.</span><span class="sxs-lookup"><span data-stu-id="17839-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17839-122">Esse valor é o bitmask que deve ser aplicado à sub-rede que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="17839-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="17839-123">Em **ID de site de rede**, selecione o site ao qual esta sub-rede pertence.</span><span class="sxs-lookup"><span data-stu-id="17839-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="17839-124">Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa sub-rede que não pode ser expressa apenas pelo nome.</span><span class="sxs-lookup"><span data-stu-id="17839-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="17839-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="17839-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="17839-126">Para modificar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="17839-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="17839-127">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="17839-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17839-128">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17839-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17839-129">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="17839-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17839-130">Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, clique em **sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="17839-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="17839-131">Na página **sub-rede** , clique na sub-rede que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="17839-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="17839-132">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="17839-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="17839-133">Na página **Editar sub-rede** , você pode modificar o bitmask, o site de rede associado ou a descrição.</span><span class="sxs-lookup"><span data-stu-id="17839-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="17839-134">Se você modificar o bitmask, lembre-se de que a identificação da sub-rede ainda deve ser o primeiro endereço no intervalo de endereços IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="17839-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="17839-135">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="17839-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17839-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="17839-136">See Also</span></span>


[<span data-ttu-id="17839-137">Excluindo sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17839-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="17839-138">Sobre regiões de rede, sites e subredes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17839-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="17839-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="17839-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="17839-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="17839-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="17839-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="17839-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="17839-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="17839-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

