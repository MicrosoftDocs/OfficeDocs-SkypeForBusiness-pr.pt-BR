---
title: 'Lync Server 2013: Associar uma subrede a um site de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5a896af6312fecf53259ac10e72f99598d4a7e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="8f864-102">Associar uma subrede a um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f864-102">Associate a subnet with a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f864-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8f864-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8f864-104">Todas as sub-redes da sua rede devem ser associadas a um site da rede específico, pois as informações da sub-rede são usadas para determinar o site da rede em que um ponto de extremidade se encontra quando uma nova sessão é iniciada.</span><span class="sxs-lookup"><span data-stu-id="8f864-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="8f864-105">Quando o local de cada participante de uma sessão é conhecido, recursos avançados do Enterprise Voice podem aplicar essas informações para determinar como manipular a configuração ou o roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8f864-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8f864-106">Todos os endereços IP públicos configurados dos Servidores de Borda de Áudio/Vídeo em sua implantação devem ser adicionados às suas definições de configuração da rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="8f864-107">Estes endereços IP são adicionados como sub-redes com uma máscara de 32.</span><span class="sxs-lookup"><span data-stu-id="8f864-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="8f864-108">O site da rede associado deve corresponder ao site da rede configurado adequado.</span><span class="sxs-lookup"><span data-stu-id="8f864-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="8f864-109">Por exemplo, o endereço IP público que corresponde ao servidor de borda A/V no site central de Chicago seria NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="8f864-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="8f864-110">Para obter detalhes sobre endereços IP públicos, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinar requisitos de firewall e porta externo A/V para o Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="8f864-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8f864-p103">Um alerta Key Health Indicator (KHI) é disparado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede ou à sub-rede que inclui os endereços IP não está associada a um site da rede. Este alerta não será disparado mais de uma vez dentro de um período de 8 horas. A informação de alerta relevante e um exemplo são como segue:</span><span class="sxs-lookup"><span data-stu-id="8f864-p103">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8-hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="8f864-114"><STRONG>Fonte:</STRONG> Serviço de política de largura de banda do CS (básico)</span><span class="sxs-lookup"><span data-stu-id="8f864-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="8f864-115"><STRONG>Número do evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="8f864-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="8f864-116"><STRONG>Nível:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="8f864-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="8f864-117"><STRONG>Descrição:</STRONG> As sub-redes para os seguintes endereços IP: &lt;a lista de endereços&gt; IP não estão configurados ou as sub-redes não estão associadas a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="8f864-118"><STRONG>Causa:</STRONG> As sub-redes dos endereços IP correspondentes estão ausentes nas configurações de configuração de rede ou as sub-redes não estão associadas a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="8f864-119"><STRONG>Resolução:</STRONG> Adicione sub-redes correspondentes à lista de endereços IP nas configurações de configuração de rede e associe cada sub-rede a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="8f864-p104">Por exemplo, se a lista de endereços IP no alerta especifica 10.121.248.226 e 10.121.249.20, ou estes endereços IP não estão associados a uma sub-rede ou a sub-rede à qual estão associados não pertence a um site da rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes para estes endereços, você pode resolver o problema da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8f864-p104">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="8f864-122">Certifique-se de que o endereço IP 10.121.248.226 está associado à sub-rede 10.121.248.0/24 e que o endereço IP 10.121.249.20 está associado à sub-rede 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="8f864-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="8f864-123">Certifique-se de que ambas as sub-redes 10.121.248.0/24 e 10.121.249.0/24 estejam associadas a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="8f864-124">Para obter detalhes sobre como trabalhar com sub-redes de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8f864-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8f864-125">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8f864-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="8f864-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8f864-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="8f864-127">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8f864-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="8f864-128">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="8f864-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="8f864-129">Se você estiver trabalhando com um grande número de sub-redes, recomendamos o uso de um arquivo de valores separados por vírgula (CSV) para associar as sub-redes a sites.</span><span class="sxs-lookup"><span data-stu-id="8f864-129">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites.</span></span> <span data-ttu-id="8f864-130">O arquivo CSV deve ter as quatro colunas: <STRONG>IPAddress</STRONG>, <STRONG>máscara</STRONG>, <STRONG>Descrição</STRONG>e <STRONG>NetworkSiteID</STRONG>a seguir.</span><span class="sxs-lookup"><span data-stu-id="8f864-130">The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="8f864-131">Para associar uma sub-rede a um site de rede usando o Shell de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="8f864-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="8f864-132">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8f864-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8f864-133">Execute o cmdlet  **New-CsNetworkSubnet** para associar uma sub-rede a um site da rede:</span><span class="sxs-lookup"><span data-stu-id="8f864-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="8f864-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8f864-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="8f864-135">Neste exemplo, você criou uma associação entre a sub-rede 172.11.12.13 e o site da rede “Chicago”.</span><span class="sxs-lookup"><span data-stu-id="8f864-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="8f864-136">Repita a etapa 2 para todas as sub-redes em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="8f864-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="8f864-137">Para associar sub-redes a sites da rede importando um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="8f864-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="8f864-p106">Crie um arquivo CSV que inclui todas as sub-redes que deseja adicionar. Por exemplo, crie um arquivo chamado **subnet.csv** como o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="8f864-p106">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="8f864-140">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8f864-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8f864-141">Execute o cmdlet a seguir para importar o **subnet. csv**e, em seguida, armazenar seu conteúdo na loja de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8f864-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="8f864-142">Para associar uma sub-rede a um site de rede usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8f864-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8f864-143">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f864-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8f864-144">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8f864-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8f864-145">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="8f864-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8f864-146">Clique no botão de navegação **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="8f864-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="8f864-147">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8f864-147">Click **New**.</span></span>

5.  <span data-ttu-id="8f864-148">Na página **Nova Sub-rede**, clique em **ID da Sub-rede** e digite o primeiro endereço do intervalo de endereços IP definido pela sub-rede que deseja associar a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="8f864-149">Clique em **Máscara** e digite o bitmask a ser aplicado à sub-rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="8f864-150">Clique em **ID do site da rede** e selecione o ID do site para o qual está adicionando esta sub-rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8f864-151">Se os sites da rede ainda não estiverem criados, a lista estará vazia.</span><span class="sxs-lookup"><span data-stu-id="8f864-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="8f864-152">Para obter detalhes sobre o procedimento, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8f864-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="8f864-153">Você também pode recuperar as IDs do site para sua implantação executando o cmdlet <STRONG>Get-CsNetworkSite</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8f864-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="8f864-154">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8f864-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="8f864-155">Opcionalmente, clique em  **Descrição** e digite informações adicionais para descrever esta sub-rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="8f864-156">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8f864-156">Click **Commit**.</span></span>

<span data-ttu-id="8f864-157">Repita estas etapas para adicionar outras sub-redes a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="8f864-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

