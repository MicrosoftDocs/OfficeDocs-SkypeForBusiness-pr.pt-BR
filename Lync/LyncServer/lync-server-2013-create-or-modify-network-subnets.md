---
title: 'Lync Server 2013: criar ou modificar sub-redes de rede'
description: 'Lync Server 2013: criar ou modificar sub-redes de rede.'
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
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546917"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="ea886-103">Criar ou modificar sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea886-103">Create or modify network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea886-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ea886-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ea886-105">É necessário associar uma subrede da rede com um site de rede para fins de determinar o local geográfico do host que pertence a esta subrede.</span><span class="sxs-lookup"><span data-stu-id="ea886-105">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="ea886-106">Você pode usar o painel de controle do Lync Server para configurar sub-redes.</span><span class="sxs-lookup"><span data-stu-id="ea886-106">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="ea886-107">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma sub-rede de rede.</span><span class="sxs-lookup"><span data-stu-id="ea886-107">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="ea886-108">Para obter detalhes sobre como excluir sub-redes de rede, consulte [excluindo sub-redes de rede no Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="ea886-108">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="ea886-109">Na maioria das implantações do Microsoft Lync Server 2013 onde o controle de admissão de chamadas (CAC) é implementado, normalmente haverá um grande número de sub-redes.</span><span class="sxs-lookup"><span data-stu-id="ea886-109">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ea886-110">Por isso, geralmente é melhor configurar sub-redes a partir do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea886-110">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="ea886-111">A partir daí, você pode chamar **New-CsNetworkSubnet** em conjunto com o cmdlet **Import-CSV**do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea886-111">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="ea886-112">Usando estes cmdlets em conjunto, é possível ler nas configurações de subrede de um arquivo de valores separados por vírgula (.csv) e criar várias subredes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ea886-112">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="ea886-113">Para obter exemplos de como criar sub-redes a partir de um arquivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="ea886-113">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="ea886-114">Para criar uma sub-rede</span><span class="sxs-lookup"><span data-stu-id="ea886-114">To create a network subnet</span></span>

1.  <span data-ttu-id="ea886-115">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ea886-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ea886-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea886-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea886-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ea886-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ea886-118">Na barra de navegação à esquerda, clique em **Configuração da rede** e clique em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="ea886-118">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ea886-119">Na página **Sub-rede** clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ea886-119">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="ea886-p104">Em **Nova Sub-rede**, digite um valor no campo **ID da sub-rede**. Esse valor deve ser um endereço IP (por exemplo, 174.11.12.0) e deve ser o primeiro endereço no intervalo de endereço IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="ea886-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="ea886-122">No campo **Máscara**, digite um valor numérico de 1 a 32.</span><span class="sxs-lookup"><span data-stu-id="ea886-122">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea886-123">Este valor é o bitmask que será aplicado na sub-rede criada.</span><span class="sxs-lookup"><span data-stu-id="ea886-123">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="ea886-124">Em **ID do site da rede**, selecione o site ao qual a sub-rede pertence.</span><span class="sxs-lookup"><span data-stu-id="ea886-124">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="ea886-125">(Opcional) Digite um valor no campo **Descrição** para fornecer mais informações essa sub-rede que não pode ser expressa somente pelo nome.</span><span class="sxs-lookup"><span data-stu-id="ea886-125">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="ea886-126">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ea886-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="ea886-127">Para modificar uma sub-rede de rede</span><span class="sxs-lookup"><span data-stu-id="ea886-127">To modify a network subnet</span></span>

1.  <span data-ttu-id="ea886-128">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ea886-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ea886-129">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea886-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea886-130">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ea886-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ea886-131">Na barra de navegação à esquerda, clique em **Configuração da rede** e clique em **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="ea886-131">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ea886-132">Na página **Sub-rede**, clique na sub-rede que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="ea886-132">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="ea886-133">No menu **Editar**, clique **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ea886-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ea886-p106">Na página **Editar sub-rede**, é possível modificar o bitmask, o local de rede associado ou a descrição. Se for mudar o bitmask, tenha em mente que o ID da sub-rede deve ser ainda o primeiro endereço do intervalo de endereço IP definido pela sub-rede.</span><span class="sxs-lookup"><span data-stu-id="ea886-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="ea886-136">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ea886-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea886-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="ea886-137">See Also</span></span>


[<span data-ttu-id="ea886-138">Excluindo sub-redes de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea886-138">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="ea886-139">Sobre regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea886-139">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="ea886-140">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ea886-140">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="ea886-141">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ea886-141">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="ea886-142">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ea886-142">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="ea886-143">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ea886-143">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

