---
title: 'Lync Server 2013: criar ou modificar uma região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3579286f0cf4b77c84baa013aead13b3b671549c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="2a0a6-102">Criar ou modificar uma região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a0a6-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a0a6-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2a0a6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2a0a6-104">*Regiões de rede* são hubs de rede ou backbones usados na configuração do serviço de controle de admissão de chamadas, E9-1-1 e desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="2a0a6-105">Execute os procedimentos a seguir para criar ou modificar as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="2a0a6-106">Por exemplo, se você já criou regiões de rede para um recurso de Voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="2a0a6-107">Porém, talvez seja necessário modificar uma definição de região de rede existente para aplicar configurações específicas ao recurso.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="2a0a6-108">Por exemplo, se você cria regiões de rede para o E9-1-1 (que não exige um local central associado) e depois implanta o controle de admissão de chamadas, precisará modificar as definições de região de rede para especificar um local central.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="2a0a6-109">Para obter detalhes, consulte [Configure Network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="2a0a6-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a0a6-110">Quaisquer requisitos específicos ao recurso para definições de região de rede são documentados nos tópicos de Implantação do recurso.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="2a0a6-111">Para obter detalhes sobre como trabalhar com regiões de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2a0a6-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="2a0a6-112">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2a0a6-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="2a0a6-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2a0a6-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="2a0a6-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2a0a6-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="2a0a6-115">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2a0a6-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="2a0a6-116">Criar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="2a0a6-116">Create a Network Region</span></span>

<span data-ttu-id="2a0a6-117">Crie uma região de rede que pode ser usada pelo controle de admissão de chamada, E9-1-1 ou bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="2a0a6-118">Para criar uma região de rede usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="2a0a6-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="2a0a6-119">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a0a6-120">Execute o cmdlet New-CsNetworkRegion para criar regiões de rede:</span><span class="sxs-lookup"><span data-stu-id="2a0a6-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="2a0a6-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2a0a6-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="2a0a6-122">Neste exemplo, você criou uma região de rede chamada “NorthAmerica” que é associada a um site central com o ID de site CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="2a0a6-123">Para concluir a criação das regiões de rede para sua topologia, repita a etapa 2 com as configurações para cada região de rede.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="2a0a6-124">Para criar uma região de rede usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="2a0a6-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2a0a6-125">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2a0a6-126">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2a0a6-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="2a0a6-127">Na barra de navegação à esquerda, clique em **Configuração de Rede**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="2a0a6-128">Clique em **Região**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-128">Click **Region**.</span></span>

4.  <span data-ttu-id="2a0a6-129">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-129">Click **New**.</span></span>

5.  <span data-ttu-id="2a0a6-130">Na página **Nova Região**, clique em **Nome** e digite um nome para a região de rede.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="2a0a6-131">Clique em **Site central** e clique em um site central na lista.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="2a0a6-132">Como opção, clique em **Descrição** e digite as informações adicionais para descrever esse site de rede.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="2a0a6-133">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="2a0a6-134">Para concluir a criação das regiões de rede para sua topologia, repita as etapas 4 a 8 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="2a0a6-135">Modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="2a0a6-135">Modify a Network Region</span></span>

<span data-ttu-id="2a0a6-136">Modifique as configurações de uma região de rede existente a fim de acomodar as alterações das informações básicas de região ou as alterações exigidas por um novo recurso.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="2a0a6-137">Para modificar uma região de rede usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="2a0a6-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="2a0a6-138">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a0a6-139">Execute o cmdlet Set-CsNetworkRegion para modificar uma região de rede existente:</span><span class="sxs-lookup"><span data-stu-id="2a0a6-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="2a0a6-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2a0a6-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="2a0a6-p103">Neste exemplo, você modificou uma região de rede existente chamada “NorthAmerica” (criada usando os procedimentos acima neste tópico) alterando a descrição. Se há houver uma descrição para a região “NorthAmerica”, esse comando a substituirá por esse valor; se não houver uma descrição, esse comando a definirá.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="2a0a6-143">Para modificar outras regiões de rede, repita a etapa 2 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="2a0a6-144">Para modificar uma região de rede usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="2a0a6-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2a0a6-145">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2a0a6-146">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2a0a6-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="2a0a6-147">Na barra de navegação esquerda, clique em **Configuração de Rede**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="2a0a6-148">Clique no botão de navegação **Região**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="2a0a6-149">Na tabela, clique na região de rede que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="2a0a6-150">Clique em **Editar** e em **Mostrar detalhes…**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="2a0a6-151">Na página **Editar Região**, altere os valores das configurações dessa região de rede conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="2a0a6-152">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="2a0a6-153">Para concluir a modificação das regiões de rede, repita as etapas 4 a 7 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="2a0a6-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

