---
title: 'Lync Server 2013: Configurando links de site de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33461781f0392d0e6e4fbfa21bdde8948e7a9a1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532578"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="dcef1-102">Configurando links de site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcef1-102">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcef1-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dcef1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dcef1-104">Em uma configuração de controle de admissão de chamada, você pode criar políticas entre locais de rede que definem as limitações de largura de banda entre os locais que estejam diretamente vinculados.</span><span class="sxs-lookup"><span data-stu-id="dcef1-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="dcef1-105">Quando os locais de uma rede compartilham um link direto, é possível definir limitações de largura de banda às conexões audiovisuais entre esses dois locais.</span><span class="sxs-lookup"><span data-stu-id="dcef1-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="dcef1-106">Você não pode usar o painel de controle do Lync Server para configurar as políticas de site de rede, isso só pode ser feito usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcef1-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="dcef1-107">Você pode criar, modificar e remover um link de site de rede (também conhecido como política entre sites de rede) do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcef1-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="dcef1-108">Para criar um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="dcef1-108">To create a network site link</span></span>

1.  <span data-ttu-id="dcef1-109">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="dcef1-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dcef1-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dcef1-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dcef1-111">No prompt de comando, digite o seguinte comando, substituindo os valores que são válidos para a sua configuração:</span><span class="sxs-lookup"><span data-stu-id="dcef1-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="dcef1-112">Este exemplo cria um novo link de site de rede chamado Reno \_ Portland que define as limitações de largura de banda entre os sites de rede Reno e Portland.</span><span class="sxs-lookup"><span data-stu-id="dcef1-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="dcef1-113">Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.</span><span class="sxs-lookup"><span data-stu-id="dcef1-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="dcef1-114">Para obter descrições detalhadas de parâmetros, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcef1-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="dcef1-115">Para recuperar uma lista de perfis de políticas de largura de banda que podem ser aplicada ao link de site de rede, chame o cmdlet de **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="dcef1-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="dcef1-116">Para obter detalhes, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcef1-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="dcef1-117">Para modificar um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="dcef1-117">To modify a network site link</span></span>

1.  <span data-ttu-id="dcef1-118">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="dcef1-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dcef1-119">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dcef1-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dcef1-120">Use o cmdlet **Set-CsNetworkInterSitePolicy** para modificar as propriedades de um link de site de rede fornecido.</span><span class="sxs-lookup"><span data-stu-id="dcef1-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="dcef1-121">Você pode modificar um (ou ambos) dos sites conectados e modificar o perfil da política de largura de banda associado ao link.</span><span class="sxs-lookup"><span data-stu-id="dcef1-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="dcef1-122">Veja um exemplo de como modificar o perfil de política de largura de banda de um link de site chamado Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="dcef1-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="dcef1-123">Para obter descrições detalhadas de parâmetros, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcef1-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="dcef1-124">Para excluir um link de site de rede</span><span class="sxs-lookup"><span data-stu-id="dcef1-124">To delete a network site link</span></span>

1.  <span data-ttu-id="dcef1-125">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="dcef1-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dcef1-126">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dcef1-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dcef1-127">Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede.</span><span class="sxs-lookup"><span data-stu-id="dcef1-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="dcef1-128">O exemplo a seguir exclui o \_ link de site de rede de Portland Reno:</span><span class="sxs-lookup"><span data-stu-id="dcef1-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="dcef1-129">Para obter descrições detalhadas de parâmetros, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcef1-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcef1-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="dcef1-130">See Also</span></span>


[<span data-ttu-id="dcef1-131">Cmdlets do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcef1-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="dcef1-132">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dcef1-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dcef1-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dcef1-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dcef1-134">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dcef1-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dcef1-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dcef1-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dcef1-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="dcef1-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

