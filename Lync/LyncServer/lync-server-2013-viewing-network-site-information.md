---
title: 'Lync Server 2013: exibindo informações de site de rede'
description: 'Lync Server 2013: exibindo informações de site de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b46dc91510cb5ff737977871470033374573ba8c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546217"
---
# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="7d237-103">Exibindo informações de site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d237-103">Viewing network site information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d237-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7d237-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7d237-105">Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="7d237-105">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="7d237-106">Você pode exibir as informações do site de rede no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d237-106">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="7d237-107">Para obter detalhes sobre como criar ou modificar sites de rede, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="7d237-107">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="7d237-108">Para exibir informações de site de rede no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="7d237-108">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7d237-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="7d237-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7d237-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d237-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d237-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d237-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d237-112">Na barra de navegação esquerda, clique em **Configuração de rede** e em **Local**.</span><span class="sxs-lookup"><span data-stu-id="7d237-112">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="7d237-113">Na página **Local**, clique no local que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="7d237-113">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d237-114">É possível exibir apenas informações de um local por vez.</span><span class="sxs-lookup"><span data-stu-id="7d237-114">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="7d237-115">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="7d237-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7d237-116">Exibindo informações de site de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d237-116">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7d237-117">Você pode exibir as informações do site de rede usando o Windows PowerShell e o cmdlet Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="7d237-117">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="7d237-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d237-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7d237-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="7d237-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="7d237-120">Para exibir a informação do local de rede</span><span class="sxs-lookup"><span data-stu-id="7d237-120">To view network site information</span></span>

  - <span data-ttu-id="7d237-121">Para exibir informações sobre todos os sites de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="7d237-121">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="7d237-122">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d237-122">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="7d237-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="7d237-123">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d237-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="7d237-124">See Also</span></span>


[<span data-ttu-id="7d237-125">Criando ou modificando sites de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d237-125">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="7d237-126">Excluindo um site de rede existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d237-126">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

