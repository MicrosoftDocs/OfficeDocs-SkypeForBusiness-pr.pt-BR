---
title: 'Lync Server 2013: criar ou modificar um site de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60119e137851bbaa8dc7b6735202132085bb8d34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506118"
---
# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="b4cc5-102">Criar ou modificar um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4cc5-102">Create or modify a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4cc5-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="b4cc5-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="b4cc5-104">As implantações do controle de admissão de chamadas, do E9-1-1 e do desvio de mídia se baseiam na configuração de *locais de rede*, que são definidos dentro de uma região da rede e sempre associados a ela.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="b4cc5-105">Um site de rede representa uma localização de filial, um conjunto de edifícios ou um campus.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="b4cc5-106">Locais de rede representam coleções de subredes com largura de banda semelhante.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="b4cc5-p102">Use os procedimentos a seguir para criar ou modificar sites de rede. Por exemplo, se você já criou sites de rede para um recurso de Voz, você não precisa criar sites de rede novos, outros recursos de Voz usarão esses mesmos sites. Você pode, porém, precisar modificar uma definição de site de rede existente para aplicar configurações específicas do recurso. Por exemplo, se você criou um site de rede para o E9-1-1, você precisa modificar o site de rede durante a implantação do controle de admissão de chamada para aplicar um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-p102">Use the following procedures to create or modify network sites. For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4cc5-111">Onde eles existirem, você pode encontrar exemplos e requisitos específicos para sites de rede à medida que eles pertencem a um recurso de Voz avançado na documentação de Implantação para cada recurso:</span><span class="sxs-lookup"><span data-stu-id="b4cc5-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b4cc5-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurar sites de rede para CAC no Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="b4cc5-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="b4cc5-113">Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b4cc5-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b4cc5-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b4cc5-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="b4cc5-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b4cc5-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="b4cc5-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b4cc5-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="b4cc5-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b4cc5-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="b4cc5-118">Criar um site de rede</span><span class="sxs-lookup"><span data-stu-id="b4cc5-118">Create a Network Site</span></span>

<span data-ttu-id="b4cc5-119">Criar uma região de rede que pode ser usada pelo controle de admissão de chamada, E9-1-1 ou desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="b4cc5-120">Para criar um site de rede usando o Shell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="b4cc5-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="b4cc5-121">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b4cc5-122">Execute o cmdlet do New-CsNetworkSite para criar sites de rede:</span><span class="sxs-lookup"><span data-stu-id="b4cc5-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="b4cc5-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b4cc5-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="b4cc5-124">Neste exemplo, você criou um site de rede chamado “Chicago” que está na região da rede “NorthAmerica”.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4cc5-125">A região da rede NorthAmerica já deve existir para que esse comando seja executado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="b4cc5-126">Para concluir a criação de sites de rede para a sua topologia, repita a etapa 2 com as configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="b4cc5-127">Para criar um site de rede usando o Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b4cc5-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b4cc5-128">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b4cc5-129">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4cc5-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b4cc5-130">Na barra de navegação à esquerda, clique em **Configurações de rede**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b4cc5-131">Clique no botão de navegação **Site**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="b4cc5-132">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-132">Click **New**.</span></span>

5.  <span data-ttu-id="b4cc5-133">Na página **Novo Site**, clique em **Nome** e depois digite um nome para o site de rede.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="b4cc5-134">Clique em **Região**, e depois clique em uma região na lista.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="b4cc5-135">De modo opcional, clique em **Política de largura de banda** e depois clique em uma das larguras de banda da lista.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4cc5-136">A política de largura de banda é solicitada apenas se você implantar o controle de admissão de chamada no site.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="b4cc5-137">De modo opcional, clique em **Política de Local**, depois clique em uma política de local na lista.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4cc5-138">A política de local é solicitada se você implantar E9-1-1 no site.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="b4cc5-139">De modo opcional, clique em **Descrição**, e depois digite as informações adicionais para descrever o site de rede.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="b4cc5-140">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-140">Click **Commit**.</span></span>

11. <span data-ttu-id="b4cc5-141">Para concluir a criação de sites de rede para a sua topologia, repita as etapas 4 a 10 com as configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="b4cc5-142">Modificar um site de rede</span><span class="sxs-lookup"><span data-stu-id="b4cc5-142">Modify a Network Site</span></span>

<span data-ttu-id="b4cc5-143">Modificar uma região de rede que pode ser usada pelo controle de admissão, E9-1-1 ou desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="b4cc5-144">Para modificar um site de rede</span><span class="sxs-lookup"><span data-stu-id="b4cc5-144">To modify a network site</span></span>

1.  <span data-ttu-id="b4cc5-145">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b4cc5-146">Execute o cmdlet Set-CsNetworkSite para modificar os sites de rede:</span><span class="sxs-lookup"><span data-stu-id="b4cc5-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="b4cc5-147">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b4cc5-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="b4cc5-p104">Neste exemplo, o site chamado “Albuquerque” é movido para a região “NorthAmerica”. Para modificar a configuração do site de rede para implantar o controle de admissão de chamada, o E9-1-1 ou desvio de mídia, modifique o site de rede executando o cmdlet Set-CsNetworkSite ou com os parâmetros do BWPolicyProfileID ou do LocationPolicy, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b4cc5-p105">Embora o parâmetro do BypassID exista para o desvio de mídia, recomendamos que você não sobreponha IDs de desvio geradas automaticamente. Você não precisa especificar parâmetros adicionais para configurar um site de rede para o desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="b4cc5-152">Para concluir a modificação dos sites de rede para sua topologia, repita a etapa 2 com as configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="b4cc5-153">Para modificar um site de rede usando um Painel de Controle Lync Server</span><span class="sxs-lookup"><span data-stu-id="b4cc5-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b4cc5-154">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b4cc5-155">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4cc5-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b4cc5-156">Na barra de navegação à esquerda, clique em **Configurações de rede**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b4cc5-157">Clique no botão de navegação **Site**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="b4cc5-158">Na tabela, clique no site de rede que você quer modificar.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="b4cc5-159">Clique em **Editar**, e depois clique em **Mostra detalhes…**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="b4cc5-160">Na página **Editar Site**, mude os valores dessas configurações de site de rede conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="b4cc5-161">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="b4cc5-162">Para concluir a modificação de sites de rede, repita as etapas de 4 a 7 com configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="b4cc5-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

