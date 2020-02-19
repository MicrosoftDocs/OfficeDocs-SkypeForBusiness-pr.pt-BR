---
title: 'Lync Server 2013: exibindo informações de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba46c4ab3ed7fd6930faf359bc964605285a953
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="d5538-102">Exibindo informações de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5538-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5538-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d5538-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d5538-104">Uma região de rede interconecta várias partes de uma rede entre várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="d5538-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d5538-105">Cada região de rede deve ser associada com um local central.</span><span class="sxs-lookup"><span data-stu-id="d5538-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d5538-106">O local central é o local do centro de dados no qual o serviço da política de largura de banda CAC está funcionando.</span><span class="sxs-lookup"><span data-stu-id="d5538-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d5538-107">Você pode usar o painel de controle do Lync Server para exibir as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="d5538-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="d5538-108">As regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet são permitidos para conexões de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="d5538-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d5538-109">Use este tópico para exibir as regiões de rede existentes.</span><span class="sxs-lookup"><span data-stu-id="d5538-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="d5538-110">Para obter detalhes sobre como criar ou modificar regiões de rede existentes, consulte [criar ou modificar regiões de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="d5538-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="d5538-111">Para exibir informações sobre uma região de rede com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="d5538-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d5538-112">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d5538-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d5538-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5538-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d5538-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d5538-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d5538-115">Na barra de navegação à direita, clique em **Configuração de Rede** e clique em **Região**.</span><span class="sxs-lookup"><span data-stu-id="d5538-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="d5538-116">Na página **região** , clique na região que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d5538-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5538-117">Você só pode exibir uma região por vez.</span><span class="sxs-lookup"><span data-stu-id="d5538-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="d5538-118">No painel **Ações**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d5538-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d5538-119">Exibindo informações de região de rede usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5538-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d5538-120">Você pode exibir as informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="d5538-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="d5538-121">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5538-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d5538-122">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="d5538-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="d5538-123">Para exibir informações de região de rede</span><span class="sxs-lookup"><span data-stu-id="d5538-123">To view network region information</span></span>

  - <span data-ttu-id="d5538-124">Para exibir informações sobre todas as suas regiões de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d5538-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="d5538-125">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5538-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="d5538-126">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="d5538-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5538-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="d5538-127">See Also</span></span>


[<span data-ttu-id="d5538-128">Criar ou modificar regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5538-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="d5538-129">Excluindo regiões de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5538-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

