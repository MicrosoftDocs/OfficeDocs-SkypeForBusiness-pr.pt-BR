---
title: 'Lync Server 2013: exibindo informações de site de rede'
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
ms.openlocfilehash: 9a63f8abe0adb2f17a674474cbf91884bef5d389
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535618"
---
# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="b493a-102">Exibindo informações de site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b493a-102">Viewing network site information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b493a-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b493a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b493a-104">Sites da rede são os escritórios ou locais configurados em cada região de um CAC (controle de admissão de chamadas) ou implantação do 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="b493a-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="b493a-105">Você pode exibir as informações do site de rede no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b493a-105">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="b493a-106">Para obter detalhes sobre como criar ou modificar sites de rede, consulte [criando ou modificando sites de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="b493a-106">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="b493a-107">Para exibir informações de site de rede no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b493a-107">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b493a-108">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b493a-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b493a-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b493a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b493a-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b493a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b493a-111">Na barra de navegação esquerda, clique em **Configuração de rede** e em **Local**.</span><span class="sxs-lookup"><span data-stu-id="b493a-111">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="b493a-112">Na página **Local**, clique no local que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="b493a-112">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b493a-113">É possível exibir apenas informações de um local por vez.</span><span class="sxs-lookup"><span data-stu-id="b493a-113">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="b493a-114">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b493a-114">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b493a-115">Exibindo informações de site de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b493a-115">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b493a-116">Você pode exibir as informações do site de rede usando o Windows PowerShell e o cmdlet Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="b493a-116">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="b493a-117">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b493a-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b493a-118">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b493a-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="b493a-119">Para exibir a informação do local de rede</span><span class="sxs-lookup"><span data-stu-id="b493a-119">To view network site information</span></span>

  - <span data-ttu-id="b493a-120">Para exibir informações sobre todos os sites de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="b493a-120">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="b493a-121">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="b493a-121">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="b493a-122">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="b493a-122">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b493a-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="b493a-123">See Also</span></span>


[<span data-ttu-id="b493a-124">Criando ou modificando sites de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b493a-124">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="b493a-125">Excluindo um site de rede existente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b493a-125">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

