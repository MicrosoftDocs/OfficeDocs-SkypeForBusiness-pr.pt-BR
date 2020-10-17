---
title: 'Lync Server 2013: exibindo informações de link de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69040594a04d71f07d004826e4207c0b23612f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535688"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="d7846-102">Exibindo informações de link de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7846-102">Viewing network region link information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7846-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d7846-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d7846-104">Você pode visualizar os links entre duas regiões de redes como parte do controle de admissão de chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="d7846-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="d7846-105">Regiões dentro de uma rede são vinculadas por conectividade de WAN física.</span><span class="sxs-lookup"><span data-stu-id="d7846-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="d7846-106">Você pode usar o painel de controle do Lync Server para exibir um link existente entre duas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="d7846-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="d7846-107">Para obter detalhes sobre como criar ou modificar um link de região de rede, confira [Configurando links de região de rede no Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="d7846-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="d7846-108">Para exibir um link de região de rede no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="d7846-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d7846-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d7846-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d7846-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7846-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d7846-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d7846-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d7846-112">Na barra de navegação esquerda, clique em **Configuração da rede** e em **Link da região**.</span><span class="sxs-lookup"><span data-stu-id="d7846-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="d7846-113">Na página **Link da região**, clique no link da região que você deseja ver.</span><span class="sxs-lookup"><span data-stu-id="d7846-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d7846-114">Você pode ver informações somente sobre um link da região por vez.</span><span class="sxs-lookup"><span data-stu-id="d7846-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="d7846-115">No menu**Editar**, selecione **Mostras detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d7846-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d7846-116">Exibindo informações de link de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7846-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d7846-117">Você pode exibir os links de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="d7846-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="d7846-118">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7846-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d7846-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="d7846-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="d7846-120">Para ver informações do link de região de rede</span><span class="sxs-lookup"><span data-stu-id="d7846-120">To view network region link information</span></span>

  - <span data-ttu-id="d7846-121">Para exibir informações sobre todos os seus links de região de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d7846-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="d7846-122">Esse comando retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="d7846-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="d7846-123">Para detalhes, consulte [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="d7846-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d7846-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="d7846-124">See Also</span></span>


[<span data-ttu-id="d7846-125">Configurando links de site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7846-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

